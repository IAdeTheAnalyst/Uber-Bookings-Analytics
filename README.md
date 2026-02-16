# Uber Booking Analytics — MySQL Data Analysis

In this project, I analyzed ride-booking operational data using a transactional bookings dataset in MySQL 8 (Workbench). My objective was to evaluate demand patterns, operational efficiency, cancellation behavior, revenue performance, and customer experience metrics to generate actionable product and operations insights.

Through structured SQL analysis and performance-based segmentation, I identified trends across time-of-day demand, vehicle categories, cancellation drivers, payment behavior, and revenue efficiency. This analysis simulates how a data analyst would support decision-making in a mobility or on-demand platform environment.

---

## Project Objectives
In this analysis, I aimed to answer the following business questions:
1. What are the **top customer cancellation reasons** and how frequently does each occur?
2. How do **driver vs. customer cancellations** compare overall and over time?
3. What are the **average wait (VTAT)** and **completion (CTAT)** times by **vehicle type**?
4. Which **pickup locations** generate the highest **total booking value**?
5. How do **customer ratings** vary by **vehicle type**?
6. What is the **payment method mix** (share of rides)?
7. Which **vehicle type** yields the highest **revenue per kilometer**?
8. During which **time-of-day** do bookings peak, and how does this differ on **weekdays vs. weekends**?

---

## Tools & Technical Approach
In this project, I used:
- **SQL (MySQL 8+)** with **MySQL Workbench**
- **CTEs**, **Aggregations** (`SUM`, `COUNT`, `AVG`, `ROUND`)
- **Window Functions** (`SUM() OVER ()`)
- **CASE** bucketing, **DATE/TIME** functions (`HOUR()`, `DAYNAME()`)
- **Data Cleaning** (`RENAME COLUMN`, `REPLACE`, `COALESCE`, `NULLIF`)
- Custom ordering with `FIELD()` for readable time-of-day output

I also calculated derived performance metrics such as revenue per kilometer and cancellation rates to measure operational efficiency.
---

## Key Insights/ Results 
Through this analysis, I discovered:
- Certain cancellation reasons consistently accounted for the majority of customer cancellations, indicating targeted improvement opportunities.
- Driver and customer cancellation patterns differed by time-of-day, highlighting operational friction during peak hours.
- Higher-tier vehicle categories tended to produce greater revenue per kilometer but varied in rating distribution.
- Demand peaked during specific time buckets, with noticeable differences between weekday and weekend booking patterns.
- Payment method usage revealed clear customer preferences that could inform promotional strategy.

This analysis demonstrates how operational ride data can be leveraged to improve service efficiency, reduce cancellations, optimize pricing strategies, and enhance customer experience.

---

## What I Learned
Through this project, I strengthened my ability to:
- Analyze operational KPIs using SQL
- Translate raw transactional data into product-level insights
- Use time-based segmentation for demand forecasting
- Evaluate service efficiency metrics such as wait time and completion time
- Apply window functions to calculate proportional and comparative metrics
- I also gained practical insight into how ride-sharing platforms measure performance across demand, supply, and customer satisfaction dimensions.

---

## Challenges I Encountered
One challenge I faced was managing time-based grouping and ensuring accurate weekday vs. weekend segmentation. I addressed this by using built-in date functions and custom CASE logic to standardize time buckets.

Another challenge involved handling NULL values and inconsistent categorical fields. I resolved this using COALESCE and REPLACE functions to ensure accurate aggregations.

Additionally, calculating performance metrics such as revenue per kilometer required careful validation to avoid division errors, which I addressed using NULLIF safeguards.

--- 

## Dataset Overview
The primary table used in this project was:
bookings, containing:
- rdate (DATE), time (TIME)
- booking_id, booking_status
- customer_id, vehicle_type
- pickup_location, drop_location
- avg_vtat (average wait time)
- avg_ctat (average completion time)
- cancels_by_customer, cancel_reason_customer
- cancels_by_driver, cancel_reason_driver
- incomplete_rides, incomplete_reason
- booking_value, ride_distance
- driver_rating, customer_rating
- payment_method


# 🚗 Uber Booking Analytics — MySQL Data Analysis

This project analyzes ride-booking operations using a transactional **bookings** dataset. By evaluating demand across time buckets, locations, vehicle types, and payment methods in **MySQL 8 (Workbench)**, it measures service speed, cancellations, ratings, and revenue efficiency to inform product & operations decisions.

---

## 🧠 Key Business Questions
1. What are the **top customer cancellation reasons** and how frequently does each occur?
2. How do **driver vs. customer cancellations** compare overall and over time?
3. What are the **average wait (VTAT)** and **completion (CTAT)** times by **vehicle type**?
4. Which **pickup locations** generate the highest **total booking value**?
5. How do **customer ratings** vary by **vehicle type**?
6. What is the **payment method mix** (share of rides)?
7. Which **vehicle type** yields the highest **revenue per kilometer**?
8. During which **time-of-day** do bookings peak, and how does this differ on **weekdays vs. weekends**?

---

## 📊 Tools Used
- **SQL (MySQL 8+)** with **MySQL Workbench**
- **CTEs**, **Aggregations** (`SUM`, `COUNT`, `AVG`, `ROUND`)
- **Window Functions** (`SUM() OVER ()`)
- **CASE** bucketing, **DATE/TIME** functions (`HOUR()`, `DAYNAME()`)
- **Data Cleaning** (`RENAME COLUMN`, `REPLACE`, `COALESCE`, `NULLIF`)
- Custom ordering with `FIELD()` for readable time-of-day output

---

## 📂 Dataset Overview
**Table:** `bookings`  
`rdate` (DATE), `time` (TIME), `booking_id`, `booking_status`,  
`customer_id`, `vehicle_type`, `pickup_location`, `drop_location`,  
`avg_vtat` (avg wait), `avg_ctat` (avg completion),  
`cancels_by_customer`, `cancel_reason_customer`,  
`cancels_by_driver`, `cancel_reason_driver`,  
`incomplete_rides`, `incomplete_reason`,  
`booking_value`, `ride_distance`,  
`driver_rating`, `customer_rating`, `payment_method`.



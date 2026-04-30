# goit-rdb-hw-07
домашка по 7 лекції
# 📊 SQL Homework: Date Functions & JSON (Orders Table)

![MySQL](https://img.shields.io/badge/MySQL-Workbench-blue)
![SQL](https://img.shields.io/badge/SQL-Functions-green)
![Status](https://img.shields.io/badge/status-completed-success)

---

## 📌 Overview

This section demonstrates working with:

- Date extraction functions
- Date arithmetic
- Timestamp conversion
- Filtering by date range
- JSON object creation in SQL

All queries are based on the **`orders`** table.

---

## 🔹 1. Extract Year, Month, and Day

Display `id`, original `date`, and extract:
- year
- month
- day

```sql
SELECT 
    id,
    date,
    YEAR(date) AS order_year,
    MONTH(date) AS order_month,
    DAY(date) AS order_day
FROM orders;
```

## 🔹 2. Add One Day to Date
Display `id`, original `date`, and the result of adding one day.
```sql
SELECT 
    id,
    date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one_day
FROM orders;
```
## 🔹 3. Convert Date to Timestamp
Display `id`, original `date`, and the number of seconds since epoch.
```sql
SELECT 
    id,
    date,
    UNIX_TIMESTAMP(date) AS date_timestamp
FROM orders;
```
## 🔹 4. Count Rows in Date Range
Count how many records fall within the specified date range.
```sql
SELECT 
    COUNT(*) AS orders_count
FROM orders
WHERE date BETWEEN '1996-07-10 00:00:00' 
               AND '1996-10-08 00:00:00';
```
## 🔹 5. Create JSON Object
Display `id`, `date`, and a JSON object with these values.
```sql
SELECT 
    id,
    date,
    JSON_OBJECT(
        'id', id,
        'date', date
    ) AS order_json
FROM orders;
```
---
Skills Demonstrated
- Date manipulation (`YEAR`, `MONTH`, `DAY`)
- Date arithmetic (`DATE_ADD`)
- Timestamp conversion (`UNIX_TIMESTAMP`)
- Filtering using `BETWEEN`
- JSON creation using `JSON_OBJECT`
- Clean and structured SQL queries

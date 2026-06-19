# E-Commerce Sales Analysis Dashboard

## 📌 Project Overview
This repository hosts the *E-Commerce Sales Analysis Dashboard*, an interactive Power BI solution designed to transform transactional e-commerce data into high-impact business intelligence. The dashboard allows stakeholders to dynamically filter data by Payment Method, Coupon Code, Year, and Customer ID to evaluate customer acquisition performance, revenue sustainability, and operational metrics.

## Key Performance Indicators (KPIs)
The top KPI ribbon tracks five high-level metrics crucial for assessing overall business health:
* Total Customers:1,189 unique purchasing clients.
* Total Revenue: $1.26M in gross sales.
* Total Quantity: 3,535 total items sold.
* Total Orders: 1,200 transactions processed.
* Average Order Value (AOV): $1,054 spent per transaction.

## DAX Functions & Calculations
To build this dashboard, standard and advanced DAX (Data Analysis Expressions) formulas were utilized to aggregate transactional data, compute key ratios, and handle time-series intelligence. Below are the core functional definitions used in this model:

### 1. Total Revenue
Total Revenue = SUM('Cleaned data' [Total Price])

## 2. Total Orders
Counts the unique number of order IDS to establish the total transaction volume.

Total Orders = DISTINCTCOUNT('Cleaned data'[Order ID])

## 3. Average Order Value (AOV)
Calculates the average monetary amount spent every time a customer places an order.
Average Order Value = DIVIDE([Total Revenue], [Total Orders], 0)

































![alt text](https://github.com/udeme054/Task-4/blob/d73d162664d3403a57a01bc08dda1a4f3755399b/E-Commerce%20sales%20Analysis%20%20dashboard%20for%20project%204%20at%20Decode%20lab.jpg)
!

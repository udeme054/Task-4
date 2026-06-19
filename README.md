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

## 4. Revenue per Customer
An efficiency metric calculated by dividung total revenue by total number of uniue customers over a specific period
Revenue per customer = Divide ([Total revenue],[Total customers])

## 5. Total Quantity
The gross volume of individual items sold across all transactions during a given period
Total Quantity = Sum('Cleaned data' [Quantity])

## 6. Total Customers
The unique number of individual buyers who have completed at least one transaction within a specific timeframe.
Total Customers = DISTINCTCOUNT('Cleaned data'[CustomerID])

Key Insights
📈 Revenue peaked in June ($171K), indicating a strong mid-year sales performance.
📉 A noticeable decline in revenue and orders occurred from July to September, suggesting possible seasonal demand fluctuations.
🪑 Chair ($196K) and Printer ($196K) generated the highest revenue among all products, making them top-performing product categories.
📱 Phone ($152K) generated the lowest revenue, presenting an opportunity for sales improvement.
💳 Credit Card ($264K) and Online Payments ($262K) were the most preferred payment methods, contributing the highest revenue.
📢 Instagram ($276K) emerged as the most effective referral source, outperforming Email, Google, Facebook, and direct referrals.
📦 Order statuses are relatively balanced, indicating a stable order fulfillment process, though cancellations and returns still require attention.



































![alt text](https://github.com/udeme054/Task-4/blob/d73d162664d3403a57a01bc08dda1a4f3755399b/E-Commerce%20sales%20Analysis%20%20dashboard%20for%20project%204%20at%20Decode%20lab.jpg)
!

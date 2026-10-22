# E-Commerce Sales Analysis Dashboard (Power BI)

## Table of Contents
1. [Project Title](#e-commerce-sales-analysis-dashboard-power-bi)
2. [Project Overview](#project-overview)
3. [Business Objectives](#business-objectives)
4. [Business Questions](#business-questions)
5. [Dataset Description](#dataset-description)
6. [DAX Measures Used](#dax-measures-used)
7. [Tools Used](#tools-used)
8. [Data Cleaning Process](#data-cleaning-process)
9. [KPIs](#kpis)
10. [Visualizations Created](#visualizations-created)
11. [Key Findings](#key-findings)
12. [Business Insights](#business-insights)
13. [Recommendations](#recommendations)
14. [Skills Demonstrated](#skills-demonstrated)
15. [Conclusion](#conclusion)
16. [Author](#author)

---

## Project Overview
This project, completed at Decode Lab, analyzes 1,200 e-commerce orders placed between January 2023 and June 2025. I built an interactive Power BI dashboard that shows revenue and order trends, top products, referral sources, payment methods and order status, with slicers for payment method, coupon code, year and customer.

## Business Objectives
- Track overall sales performance through core KPIs.
- Understand monthly revenue and order patterns.
- Identify the top-performing products, referral sources and payment methods.
- Monitor order fulfillment through order status.
- Provide data-driven recommendations to grow revenue and improve operations.

## Business Questions
1. What are the overall sales KPIs (customers, revenue, quantity, orders and average order value)?
2. How do revenue and orders change by month, and when do they peak?
3. Which products generate the most revenue?
4. Which referral sources bring in the most revenue?
5. Which payment methods are most used?
6. How are orders split by status, and how serious are cancellations and returns?

## Dataset Description
Source: `Cleaned_Data.xlsx` (table: *Cleaned Data*), containing **1,200 orders and 16 columns**, from January 1, 2023 to June 30, 2025.

| Column | Description |
|---|---|
| Order ID, Tracking Number | Unique order and shipment identifiers |
| Order Date, Month, Year | When the order was placed |
| Customer ID | Customer identifier (1,189 unique customers) |
| Product | Chair, Printer, Laptop, Tablet, Monitor, Desk or Phone |
| Quantity, Price | Units ordered and unit price |
| Revenue | Quantity x Price |
| Payment Method | Credit Card, Online, Cash, Gift Card or Debit Card |
| Order Status | Cancelled, Returned, Pending, Shipped or Delivered |
| Coupon Code | FREESHIP, WINTER15, SAVE10 or NO COUPON |
| Referral Source | Instagram, Email, Google, Facebook or Referral |
| Address | Delivery address |
| Delivery Time | Days value (1 to 10) |

## DAX Measures Used
Measures are stored in a dedicated `_Measures` table. Column names below are illustrative; adjust them to match your model.

```DAX
Total Revenue       = SUM('Cleaned Data'[Revenue])
Total Quantity      = SUM('Cleaned Data'[Quantity])
Total Orders        = DISTINCTCOUNT('Cleaned Data'[Order ID])
Total Customers     = DISTINCTCOUNT('Cleaned Data'[CustomerID])
Average Order Value = DIVIDE([Total Revenue], [Total Orders])
```

## Tools Used
- **Power BI Desktop**: data modeling, DAX and dashboard design
- **Power Query**: data preparation
- **Excel**: cleaned source data
- **GitHub**: documentation and version control

## Data Cleaning Process

| Check | Result | Action |
|---|---|---|
| Missing values | None in any column | None needed |
| Duplicate records | No duplicate rows, order IDs or tracking numbers | None needed |
| Dates | All valid, ranging from Jan 2023 to Jun 2025 | Set to Date type; created Month and Year columns (consistent with every order date) |
| Revenue | Recalculated as Quantity x Price | Matches on all 1,200 rows |
| Categories | Product, payment method, status, coupon and referral values are consistent | None needed |
| Model | Measures kept separate from data | Created a `_Measures` table |

**Notes:** Revenue includes orders of every status (including cancelled and returned), and 2025 contains only six months of data. Both affect how the results should be read.

## KPIs

| Total Customers | Total Revenue | Total Quantity | Total Orders | Avg Order Value |
|:---:|:---:|:---:|:---:|:---:|
| **1,189** | **$1.26M** | **3,535** | **1,200** | **$1,054** |

## Visualizations Created
- **KPI cards**: Total Customers, Revenue, Quantity, Orders and Average Order Value
- **Line chart**: Monthly Revenue
- **Line chart**: Monthly Orders
- **Bar chart**: Products by Revenue
- **Bar chart**: Referral Sources by Revenue
- **Column chart**: Payment Methods by Revenue
- **Donut chart**: Orders by Order Status
- **Slicers**: Payment Method, Coupon Code, Year, Customer ID
- **Key Insights panel**: Text summary of main takeaways

## Key Findings
Answers to the business questions:

1. **Overall KPIs:** The business has **1,189 customers, $1.26M in revenue, 3,535 units sold and 1,200 orders**, with an average order value of **$1,054**.
2. **Monthly trend:** **June is the peak** with **$171K revenue and 147 orders**, and the lowest month is **September ($69K, 73 orders)**. Revenue also falls from July to December, but part of this is because 2025 only has data up to June.
3. **Products:** **Chair ($196K) and Printer ($196K)** are the top products and are essentially tied, followed by Laptop ($192K) and Tablet ($187K). **Phone is lowest at $152K.**
4. **Referral sources:** **Instagram leads at $275K**, followed by Email ($262K), Google and Facebook ($250K each), and Referral ($227K).
5. **Payment methods:** **Credit Card ($264K) and Online ($262K)** bring in the most revenue. Online has the most orders (258), and Debit Card is lowest ($232K).
6. **Order status:** Orders are spread evenly: Cancelled 250 (20.8%), Returned 247 (20.6%), Pending 237 (19.8%), Shipped 234 (19.5%) and Delivered 231 (19.3%). **Cancelled and returned orders make up 41% of all orders.**

## Business Insights
- **Fulfillment is the biggest concern.** Only about 19% of orders are marked Delivered, and 41% are cancelled or returned. Since revenue counts every status, the true realized revenue is lower than $1.26M.
- **June is a strong seasonal peak.** It is the best month overall and the top month in both 2024 ($68K) and 2025 ($53K).
- **The July to September "drop" is smaller than it looks.** Averaged per year of data, second-half revenue is only about 5% below first-half revenue.
- **Sales are declining year over year.** Revenue for January to June fell from $287K (2023) to $257K (2024) and $232K (2025), roughly 10% a year.
- **Revenue is evenly spread.** The five top products are within $20K of each other, and referral sources and payment methods are also close, so there is no heavy dependence on one.
- **Instagram is the strongest acquisition channel**, while direct referrals are the weakest.
- **Repeat purchasing is almost non-existent.** There are 1,189 customers for 1,200 orders, so only about 1% of orders come from returning customers.
- **Coupons do not change order value.** Average order value is about $1,040 to $1,070 whether or not a coupon is used, and FREESHIP is the most used code.

## Recommendations
1. **Reduce cancellations and returns** by reviewing product descriptions, delivery times and payment issues, and survey customers who cancel.
2. **Track net revenue** (excluding cancelled and returned orders) alongside total revenue for a more accurate picture.
3. **Replicate June's success** with campaigns and promotions in slower months, especially September.
4. **Invest more in Instagram and Email** and review the return on the weaker Referral program.
5. **Promote Phone** (the lowest product) with bundles or discounts, and keep stock of Chair, Printer and Laptop.
6. **Build customer loyalty** through a rewards program and follow-up emails to lift the very low repeat rate.
7. **Review the coupon strategy**, since discounts are not increasing order value.
8. **Investigate the yearly decline** in first-half sales and set recovery targets.

## Skills Demonstrated
- Data validation and cleaning
- Data modeling and DAX measures
- KPI design and interactive dashboards with slicers
- Data visualization and storytelling
- E-commerce and sales analytics
- Business insight generation and recommendations
- Documentation (GitHub README)

## Conclusion
The business recorded **$1.26M in revenue from 1,200 orders and 1,189 customers**, with an average order value of $1,054. Sales are spread evenly across products, channels and payment methods, with June as the peak and Instagram as the best channel. However, the high share of cancelled and returned orders (41%), declining year-over-year sales and almost no repeat customers are the main areas to fix.

# Photo Gallery for dashboard
![alt text](https://github.com/udeme054/Task-4/blob/8da34836693aeeafc9f6c6b67404d849aa64015d/E-Commerce%20Sales%20Dashboard%20Project%204/E-Commerce%20sales%20Analysis%20%20dashboard%20for%20project%204%20at%20Decode%20lab.jpg)

## Author
**Udeme Jackson**
Data Analyst
[LinkedIn](https://lnkd.in/p/e_rSEdTM) 
[GitHub](https://github.com/udeme054/Task-4/tree/main/E-Commerce%20Sales%20Dashboard%20Project%204)

# Retail Sales Analysis | Power BI Dashboard

An interactive Power BI dashboard that analyzes retail sales performance across product categories, regions, and time. It turns raw transaction data into clear KPIs and visuals so business users can see what drives revenue and profit.

---


## Project Overview

This project analyzes retail sales data from **January 2023 to December 2025** covering about **50K orders**. The dashboard summarizes sales, profit, orders, and profit margin, and breaks them down by product category, region, and time.

## Project Dashboard Overview 

![Retail Sales Project](/SS.Png)

**Headline numbers**

| KPI | Value |
|---|---|
| Total Sales | 150.68M |
| Total Profit | 67.83M |
| Total Orders | 50K |
| Average Order Value | 3.01K |
| Profit Margin | 45.02% |

---

## Business Objectives

- Track overall sales and profit performance 
- Identify the best and worst performing product categories
- Compare performance across regions (North, South, East, West)
- Understand sales trends and seasonality over time
- Support data-driven decisions on pricing, inventory, and marketing

---


## Tools and Skills

- **Power BI Desktop**
- **Power Query** for data cleaning and transformation
- **DAX** for measures and calculations
- **Data modeling** (star schema)
- **Data visualization and storytelling**

---

## Dataset

The data is organized into the following tables:

| Table | Key Fields |
|---|---|
| **Sales (fact)** | customer_ID, quantity, discount, order_date, order_id, order_status, product_id, sales_amount, store_id, unit_price |
| **products** | category, cost, price, product_id, product_name |
| **customers** | customer_id, customer_name, age, country, email |
| **employees** | employee_id, employee_name, salary, department |
| **calendar** | date, month, month_name, quarter, year |
| **regions** | region_id, region_name |
| **stores** | city, manager_id, region_id, state, store_id, store_name |



---

## Data Model

The model follows a **star schema**:

- One central **Sales** fact table
- Dimension tables: **products**, **customers**, **employees**, **calendar**,**stores**, **regions**
- One-to-many relationships from each dimension to the fact table
- The **calendar** table is marked as the date table to support time intelligence

---

## DAX Measures

| Measure | Purpose |
|---|---|
| `Total Sales` | Sum of revenue |
| `Total Profit` | Sum of profit |
| `Total Orders` | Count of orders |
| `Average Order Value` | Total Sales divided by Total Orders |
| `Profit Margin %` | Total Profit divided by Total Sales |



## Dashboard Features

**Filters**
- Date range slicer (01/01/2023 to 31/12/2025)
- Category dropdown slicer

**KPI cards**
- Total Sales, Total Profit, Total Orders, Average Order Value

**Visuals**
- **Donut charts:** Total Sales, Total Profit, and Total Orders by category
- **Gauge:** Profit Margin
- **Line chart:** Total Sales by Time
- **Clustered column chart:** Total Sales by Region and Category

---

## Key Insights

- **Electronics is the top category**, contributing about 42% of sales, 41% of profit, and 42% of orders.
- **Furniture** has the smallest share of sales (about 23%) but a slightly higher share of profit (about 25%), which suggests better profitability per sale.
- **Office Supplies** contributes roughly 35% of sales and sits in the middle on all measures.
- **North is the strongest region**, followed by South, East, and West.
- The **profit margin is 45.02%**, which is high for retail and should be validated against how cost is defined.
- Sales are stable over time with high daily volatility and no strong long-term trend.

---

## Recommendations

- Prioritize inventory and marketing for **Electronics** in the North and South regions.
- Investigate why **East and West** lag behind and whether local promotions or stock changes could help.
- Review the cost assumptions behind the 45% margin before using it for target setting.
- Plan campaigns around seasonal peaks once the monthly trend is analyzed.











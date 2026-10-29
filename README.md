# Retail Sales Analysis | Power BI Dashboard

An interactive Power BI dashboard that analyzes retail sales performance across product categories, regions, and time. It turns raw transaction data into clear KPIs and visuals so business users can see what drives revenue and profit.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Business Objectives](#business-objectives)
3. [Dataset](#dataset)
4. [Data Model](#data-model)
5. [DAX Measures](#dax-measures)
6. [Dashboard Features](#dashboard-features)
7. [Key Insights](#key-insights)
8. [Recommendations](#recommendations)
9. [Tools and Skills](#tools-and-skills)
10. [How to Use](#how-to-use)
11. [Future Improvements](#future-improvements)

---

## Project Overview

This project analyzes retail sales data from **January 2023 to December 2025** (date slicer range) covering about **50K orders**. The dashboard summarizes sales, profit, orders, and profit margin, and breaks them down by product category, region, and time.

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

- Track overall sales and profit performance at a glance
- Identify the best and worst performing product categories
- Compare performance across regions (North, South, East, West)
- Understand sales trends and seasonality over time
- Support data-driven decisions on pricing, inventory, and marketing

---

## Dataset

The data is organized into the following tables:

| Table | Key Fields |
|---|---|
| **Sales (fact)** | order ID, date, product, customer, quantity, revenue, profit |
| **products** | category, cost, price |
| **customers** | customer_id, customer_name, age, country, email |
| **employees** | employee details |
| **calendar** | date, month, month_name, quarter, year |

> Update this table to match your actual column names and data source (Excel, CSV, SQL, etc.).

---

## Data Model

The model follows a **star schema**:

- One central **Sales** fact table
- Dimension tables: **products**, **customers**, **employees**, **calendar**
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

Example:

```DAX
Total Sales = SUM(Sales[Revenue])

Profit Margin % = DIVIDE([Total Profit], [Total Sales])

Average Order Value = DIVIDE([Total Sales], [Total Orders])
```

> Adjust table and column names to match your model.

---

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

---

## Tools and Skills

- **Power BI Desktop**
- **Power Query** for data cleaning and transformation
- **DAX** for measures and calculations
- **Data modeling** (star schema)
- **Data visualization and storytelling**

---

## How to Use

1. Clone or download this repository.
2. Open the `.pbix` file in **Power BI Desktop**.
3. If prompted, update the data source path under **Home > Transform data > Data source settings**.
4. Click **Refresh** to load the latest data.
5. Use the date and category slicers to explore the dashboard.

---

## Future Improvements

- Show sales trend at **monthly** level instead of daily for clearer patterns
- Add a **target** to the profit margin gauge (e.g., 50%) and set a realistic max value
- Add **Year-over-Year growth** and rolling average measures
- Add **Top 10 products and customers** visuals
- Build a second page for **customer and employee performance**
- Add **drill-through** pages and tooltips
- Publish to **Power BI Service** with scheduled refresh and row-level security

---

## Screenshot

Add a screenshot of the dashboard here:

```markdown
![Dashboard Preview](images/dashboard.png)
```

---

## Author

**Your Name**
[LinkedIn](#) | [GitHub](#) | [Email](#)

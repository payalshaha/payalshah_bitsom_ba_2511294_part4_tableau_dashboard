# Task 1: Data Connection and Inspection

## Data Source

The dataset `dashboard_sales_data.xlsx` was connected to Tableau using the Microsoft Excel connector. The dataset contains retail transaction records covering sales, profitability, customer segments, product categories, shipping performance, discounts, and returns.

## Field Classification and Data Types

### Date Fields

| Field Name | Tableau Data Type | Purpose              |
| ---------- | ----------------- | -------------------- |
| order_date | Date              | Order placement date |
| ship_date  | Date              | Shipment date        |

### Geographic Fields

| Field Name | Tableau Data Type | Geographic Role |
| ---------- | ----------------- | --------------- |
| region     | String            | Region          |
| state      | String            | State/Province  |
| city       | String            | City            |

### Categorical Fields

| Field Name       |
| ---------------- |
| order_id         |
| customer_id      |
| customer_segment |
| category         |
| sub_category     |
| product_name     |
| ship_mode        |
| campaign_channel |

These fields were used for grouping, filtering, segmentation, and comparison analysis.

### Numerical Measures

| Field Name      | Data Type        |
| --------------- | ---------------- |
| sales           | Number (Decimal) |
| profit          | Number (Decimal) |
| discount        | Number (Decimal) |
| delivery_days   | Number (Whole)   |
| customer_rating | Number (Decimal) |

These fields were used for KPI calculations, trend analysis, profitability analysis, and operational performance evaluation.

### Binary / Flag Fields

| Field Name  | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| return_flag | Indicates whether an order was returned (1 = Returned, 0 = Not Returned) |

This field was used to calculate return rates and perform return pattern analysis.

## Data Quality Checks Performed

* Verified that date fields were recognized as Date data types.
* Confirmed sales, profit, discount, and delivery_days were imported as numeric measures.
* Checked categorical fields for consistent naming and grouping.
* Verified return_flag contains binary values suitable for return analysis.
* Reviewed geographic fields for mapping and regional analysis.

## Assumptions

1. Each record represents a single retail transaction.
2. `order_id` uniquely identifies an order.
3. `return_flag = 1` indicates a returned order and `0` indicates a non-returned order.
4. `delivery_days` represents the actual number of days between order and delivery.
5. Sales and profit values are recorded in the same currency throughout the dataset.
6. Discount values are expressed as proportions (e.g., 0.10 = 10% discount).
7. Customer ratings are recorded on a consistent rating scale across all transactions.
8. No external data sources were required for dashboard creation.

## Conclusion

The dataset was successfully loaded into Tableau, field types were validated, and the data was determined to be suitable for executive dashboard development, KPI tracking, profitability analysis, return analysis, shipping performance evaluation, and business storytelling.


# Tableau Executive Dashboard & Data Storytelling

## Business Problem Summary

The retail leadership team requires an executive dashboard to monitor overall business performance across sales, profitability, customer segments, product categories, shipping operations, discount effectiveness, and return patterns. The objective is to identify business opportunities, operational risks, and areas requiring management attention through a single interactive Tableau dashboard.

---

# Dataset Description

The dataset contains retail sales transaction data and includes information related to:

* Orders and sales transactions
* Product categories and sub-categories
* Customer segments
* Geographic regions
* Shipping modes
* Discounts and profits
* Order and shipping dates
* Return indicators

The dataset was imported into Tableau and reviewed to verify field types and data quality before dashboard development.

### Data Types Reviewed

#### Date Fields

* Order Date
* Ship Date

#### Geographic Fields

* Region
* State

#### Categorical Fields

* Category
* Sub-Category
* Customer Segment
* Ship Mode
* Campaign Channel

#### Numerical Measures

* Sales
* Profit
* Discount
* Quantity
* Delivery Days

#### Binary / Flag Fields

* Return Flag

---

# Tableau Workbook Description

The Tableau workbook (`executive_dashboard.twbx`) contains:

* Calculated fields
* Individual analysis worksheets
* KPI cards
* Interactive filters
* Dashboard actions
* Executive dashboard layout

The dashboard was designed to support leadership decision-making through interactive business performance monitoring.

---

# Calculated Fields Created

## 1. Profit Margin

```tableau
SUM([Profit]) / SUM([Sales])
```

Purpose:
Measures profitability as a percentage of sales.

---

## 2. Cost

```tableau
SUM([Sales]) - SUM([Profit])
```

Purpose:
Estimates the cost associated with generating sales.

---

## 3. Average Order Value

```tableau
SUM([Sales]) / COUNTD([Order ID])
```

Purpose:
Measures average revenue generated per order.

---

## 4. Return Rate

```tableau
SUM([Return Flag]) / COUNT([Order ID])
```

Purpose:
Measures the percentage of orders that were returned.

---

## 5. Shipping Delay Bucket

```tableau
IF [Delivery Days] <= 3 THEN "Fast"
ELSEIF [Delivery Days] <= 7 THEN "Moderate"
ELSEIF [Delivery Days] <= 14 THEN "Slow"
ELSE "Very Slow"
END
```

Purpose:
Categorizes delivery performance into business-friendly groups.

---

# Dashboard Components

The dashboard includes the following visualizations:

### KPI Cards

* Total Sales
* Total Profit
* Profit Margin
* Return Rate

### Analysis Views

1. Sales Trend View
2. Regional Performance View
3. Category Profitability View
4. Customer Segment View
5. Shipping Performance View
6. Discount vs Profit View
7. Return Analysis View

These views collectively provide a comprehensive picture of business performance.

---

# Filters and Interactions Used

## Dashboard Filters

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date
* Campaign Channel

## Dashboard Actions

A filter action was created where selecting a region in the Regional Performance View automatically filters related charts across the dashboard.

This interaction allows users to perform deeper regional analysis without navigating to separate dashboards.

---

# Key Business Insights

Key findings from the dashboard include:

1. Sales performance demonstrates identifiable growth and seasonal patterns.
2. Certain regions consistently outperform others in both sales and profitability.
3. Some product categories contribute significantly more profit than others.
4. Customer segments differ substantially in sales contribution.
5. Higher discount levels are frequently associated with lower profitability.
6. Standard shipping experiences longer delivery times compared with premium shipping methods.
7. Certain categories or regions exhibit higher return rates.
8. Profitability improvement opportunities exist through optimized discounting and operational efficiency improvements.

---

# Chart Selection Justification

## Overview

The Executive Sales Performance Dashboard was designed to help leadership monitor sales, profitability, customer behavior, shipping performance, discount effectiveness, and return patterns. Each chart was selected based on the business question it answers and follows data visualization best practices to ensure clarity, accuracy, and actionable insights.

---

# 1. Sales Trend View

## What Question Does This Chart Answer?

How are sales changing over time, and are there any growth or seasonal trends?

## Why Is This Chart Type Appropriate?

A line chart is the most effective way to visualize changes over time because it clearly shows trends, patterns, growth periods, and declines.

## Fields Used

- Columns: Order Date (Month/Year)
- Rows: Sales
- Filters: Region, Category, Customer Segment, Date

## Design Principle Applied

A continuous timeline helps users quickly identify sales trends and seasonal fluctuations.

## Mistake Avoided

Avoided using pie charts or stacked bar charts, which make trend analysis difficult.

---

# 2. Regional Performance View

## What Question Does This Chart Answer?

Which regions contribute the most sales and profit?

## Why Is This Chart Type Appropriate?

A horizontal bar chart provides a clear comparison between regions and allows easy ranking of performance.

## Fields Used

- Rows: Region
- Columns: Sales
- Color: Profit
- Filters: Category, Customer Segment

## Design Principle Applied

Regions were sorted in descending order to immediately highlight top-performing and underperforming areas.

## Mistake Avoided

Avoided unsorted charts and overly complex maps that could reduce readability.

---

# 3. Category Profitability View

## What Question Does This Chart Answer?

Which product categories and sub-categories generate the highest profit and which generate losses?

## Why Is This Chart Type Appropriate?

Bar charts provide accurate comparisons of profitability across multiple categories and clearly show differences in performance.

## Fields Used

- Rows: Category / Sub-Category
- Columns: Profit
- Color: Category
- Filters: Region, Customer Segment

## Design Principle Applied

Consistent category colors and descending sorting improve readability and comparison.

## Mistake Avoided

Avoided treemaps because exact profit differences are easier to compare using bars.

---

# 4. Customer Segment View

## What Question Does This Chart Answer?

How do customer segments compare in terms of sales and profitability?

## Why Is This Chart Type Appropriate?

Bar charts allow straightforward comparison of performance across customer segments.

## Fields Used

- Columns: Customer Segment
- Rows: Sales
- Label: Profit
- Filters: Region, Category

## Design Principle Applied

Simple layout and clear labels support quick executive-level interpretation.

## Mistake Avoided

Avoided 3D charts and excessive color variation that could distract from the comparison.

---

# 5. Shipping Performance View

## What Question Does This Chart Answer?

Which shipping methods experience the longest delivery times and delays?

## Why Is This Chart Type Appropriate?

A bar chart clearly compares average delivery times across shipping modes and highlights operational performance differences.

## Fields Used

- Rows: Ship Mode
- Columns: Average Delivery Days
- Color: Shipping Delay Bucket
- Filters: Region, Category

## Design Principle Applied

Delay categories are color-coded to help users quickly identify shipping performance issues.

## Mistake Avoided

Avoided displaying only raw tables because visual comparisons are easier and faster with charts.

---

# 6. Discount vs Profit View

## What Question Does This Chart Answer?

How does discounting affect profitability?

## Why Is This Chart Type Appropriate?

A scatter plot is ideal for examining relationships between two numerical variables and identifying trends, clusters, and outliers.

## Fields Used

- Columns: Discount
- Rows: Profit
- Color: Category
- Detail: Order ID
- Filters: Region, Customer Segment

## Design Principle Applied

Each point represents a transaction, allowing users to observe how increasing discounts affect profit outcomes.

## Mistake Avoided

Avoided line charts because discount values are not sequential time-based data.

---

# 7. Return Analysis View

## What Question Does This Chart Answer?

Which categories, regions, or customer segments have the highest return rates?

## Why Is This Chart Type Appropriate?

A bar chart provides a clear comparison of return rates and highlights areas with elevated return risk.

## Fields Used

- Rows: Category (or Region/Segment)
- Columns: Return Rate
- Color: Return Rate
- Label: Return Rate Percentage
- Filters: Region, Customer Segment

## Design Principle Applied

Return rates are displayed as percentages and sorted from highest to lowest to emphasize risk areas.

## Mistake Avoided

Avoided pie charts because small differences in return rates are difficult to compare accurately.

---

# Dashboard-Level Visualization Design Principles

## Correct Chart Selection

Each visualization was chosen based on the business question being answered. Trend analysis uses line charts, comparisons use bar charts, and relationship analysis uses scatter plots.

## Clear Hierarchy

The dashboard places KPI cards at the top, followed by trend analysis, performance comparisons, and operational insights. This structure allows leadership to review key metrics before exploring detailed analysis.

## Minimal Clutter

Unnecessary gridlines, excessive labels, and decorative elements were removed to keep the focus on business insights.

## Consistent Color Usage

The dashboard follows a consistent color scheme:

- Sales Metrics: Blue
- Profit Metrics: Green
- Losses: Red
- Return Metrics: Orange
- Shipping Delay Categories: Consistent delay-based colors

This improves readability and reduces confusion.

## Proper Labels

All charts include meaningful axis labels, category labels, and metric names. Labels are displayed only where they improve interpretation.

## Readable Titles

Each worksheet uses descriptive business-friendly titles such as:

- Monthly Sales Trend
- Regional Performance Analysis
- Category Profitability Analysis
- Customer Segment Performance
- Shipping Performance Analysis
- Discount vs Profit Relationship
- Return Rate Analysis

## Appropriate Sorting

Charts are sorted to improve readability:

- Regions sorted by sales
- Categories sorted by profit
- Return rates sorted highest to lowest
- Customer segments sorted by sales contribution

## Useful Filters

The dashboard includes interactive filters for:

- Region
- Category
- Customer Segment
- Ship Mode
- Order Date
- Campaign Channel

These filters allow users to analyze performance from multiple perspectives.

## Avoidance of Misleading Scales

The dashboard avoids common visualization problems by:

- Not using 3D charts
- Avoiding distorted axes
- Formatting percentage metrics correctly
- Using consistent scales across comparable charts

## Focus on Business Interpretation

The dashboard was designed to support decision-making rather than simply display data. Each visualization helps leadership identify growth opportunities, profitability drivers, customer behavior patterns, operational challenges, and business risks.

# Dashboard Story Summary

The dashboard reveals a business that generates strong sales across multiple markets while facing profitability challenges linked to discounting practices, shipping delays, and return behavior.

High-performing regions and categories provide growth opportunities, while underperforming areas highlight the need for targeted operational improvements. The analysis demonstrates that revenue growth alone is insufficient and should be balanced with profitability, customer satisfaction, and operational efficiency.

The dashboard supports leadership decision-making by connecting sales performance, profitability, customer behavior, logistics, and returns into a unified business narrative.

---

# Assumptions and Limitations

## Assumptions

* Date fields were correctly interpreted by Tableau.
* Return Flag values accurately represent returned orders.
* Delivery Days accurately reflect shipping performance.
* Missing values were handled appropriately during data preparation.

## Limitations

* The dashboard is based on historical data and does not predict future performance.
* External market factors are not included.
* Customer satisfaction data is unavailable.
* Return analysis identifies patterns but not root causes.
* Results depend on the accuracy and completeness of source data.

---

# Screenshots Included

The repository includes the following screenshots:

* full_dashboard.png
* sales_trend_view.png
* regional_performance_view.png
* category_profitability_view.png
* filter_interaction_view.png

These screenshots provide evidence of dashboard construction, visualizations, and interactive functionality.

---

# Repository Structure

```text
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```

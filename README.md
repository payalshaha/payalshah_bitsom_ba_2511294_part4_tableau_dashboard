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

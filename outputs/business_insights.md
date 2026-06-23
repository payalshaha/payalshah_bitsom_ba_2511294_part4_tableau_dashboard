
# Calculated Fields Used

## 1. Profit Margin

Formula:

SUM([profit]) / SUM([sales])

Purpose:
Measures the percentage of sales retained as profit. This KPI helps leadership evaluate overall profitability and compare performance across regions, categories, and customer segments.

---

## 2. Cost

Formula:

[sales] - [profit]

Purpose:
Estimates the underlying cost associated with each transaction. This field supports profitability analysis and helps identify high-cost product categories.

---

## 3. Average Order Value (AOV)

Formula:

SUM([sales]) / COUNTD([order_id])

Purpose:
Measures the average revenue generated per order. Higher AOV indicates stronger customer spending behavior and sales effectiveness.

---

## 4. Return Rate

Formula:

SUM([return_flag]) / COUNT([order_id])

Purpose:
Measures the proportion of orders returned by customers. This metric helps identify quality issues, customer dissatisfaction, or operational problems.

---

## 5. Shipping Delay Bucket

Formula:
Delivery days grouped into Fast, Normal, Delayed, and Highly Delayed categories.

Purpose:
Simplifies delivery performance analysis and helps leadership identify shipping efficiency issues and potential customer experience risks.

---

## Additional Calculated Fields

### Discount Bucket

Groups transactions based on discount levels to evaluate the relationship between discounting and profitability.

### Profit Category

Classifies transactions as profitable or loss-making, helping identify products or segments that reduce overall business performance.

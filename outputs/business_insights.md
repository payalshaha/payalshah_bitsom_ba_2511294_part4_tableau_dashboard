
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

# Business Insights

## Insight 1: Sales Trend Analysis

### Observation

Sales show a generally increasing trend over the analysis period, with noticeable peaks during specific months.

### Data Evidence

Monthly sales reached approximately **$10,861 K** during **August 2025**, while the lowest sales occurred during **August 2024**.

### Business Interpretation

The business experiences seasonal demand patterns that influence overall sales performance.

### Recommended Action

Investigate the factors driving peak sales periods and develop targeted marketing campaigns to maximize revenue during high-demand months.

---

## Insight 2: Regional Performance

### Observation

The **South** region generated the highest sales and profit, while **East** underperformed.

### Data Evidence

The top region contributed approximately **$ 64,693K** in sales and **$10M** in profit.

### Business Interpretation

Regional differences suggest varying customer demand, market penetration, or operational effectiveness.

### Recommended Action

Analyze successful strategies used in the top-performing region and evaluate whether they can be replicated in lower-performing regions.

---

## Insight 3: Category Profitability

### Observation

The **Technology/Copiers** category generated the highest profit, while **Office Supplies/Papers** generated lower profit or losses.

### Data Evidence

Profit for the leading category was approximately **$7310K** compared with **$319K** for the weakest category.

### Business Interpretation

Some product categories create significantly more value than others.

### Recommended Action

Increase focus on profitable product lines and review pricing, sourcing, or inventory strategies for low-profit categories.

---

## Insight 4: Customer Segment Behavior

### Observation

The **Home Office** customer segment generated the highest sales contribution.

### Data Evidence

The segment contributed approximately **$74501K**, representing a significant share of total revenue.

### Business Interpretation

Certain customer groups provide a larger share of business value and may respond differently to promotions and product offerings.

### Recommended Action

Develop segment-specific marketing and retention strategies to strengthen relationships with high-value customers.

---

## Insight 5: Discount Impact on Profitability

### Observation

Higher discounts are generally associated with lower profit levels. As discount rates increase, the number of low-profit and loss-making transactions becomes more frequent.

### Data Evidence

The scatter plot shows that transactions with discounts between 25% and 35% have a much higher concentration of negative-profit orders compared to transactions with discounts below 10%. Most high-profit transactions occur at discount levels between 0% and 10%.

### Business Interpretation

While discounts may help increase sales volume, excessive discounting significantly reduces profitability and increases the likelihood of loss-making transactions. The relationship suggests diminishing returns from aggressive discount strategies.

### Recommended Action

Establish discount approval thresholds, particularly for discounts above 20%. Conduct further analysis to determine which products and customer segments remain profitable at higher discount levels and optimize promotional strategies accordingly.

## Insight 6: Shipping and Delivery Performance

### Observation

Standard Class shipments experience significantly longer delivery times compared to other shipping modes. Same Day shipping consistently delivers the fastest service.

### Data Evidence

The chart shows that Standard Class has an average delivery duration of approximately 21 days, while Same Day shipping averages around 3 days. First Class and Second Class shipping modes fall between these extremes, with average delivery times of approximately 10–11 days.

### Business Interpretation

The large gap in delivery performance suggests that Standard Class shipments may be contributing to customer dissatisfaction, delayed order fulfillment, and increased operational risk. Faster shipping methods provide a substantially better customer experience but may involve higher logistics costs.

### Recommended Action

Investigate the causes of delays within Standard Class shipping and identify opportunities to improve fulfillment efficiency. Further analysis should evaluate whether delayed deliveries are associated with higher return rates, lower customer satisfaction, or reduced repeat purchases. Consider promoting faster shipping options for high-value customers and time-sensitive products.


## Insight 7: Return Pattern Analysis

### Observation

The highest return rate was observed within **Furniture/Home Office/East**.

### Data Evidence

Return rates reached approximately **12.63%**, exceeding the overall average.

### Business Interpretation

High return rates may indicate product quality issues, customer expectation mismatches, or fulfillment problems.

### Recommended Action

Conduct detailed analysis of returned products and customer feedback to identify root causes.

---

## Insight 8: Business Risk and Opportunity

### Observation

The dashboard highlights both growth opportunities and operational risks.

### Data Evidence

High-performing categories and regions continue to generate strong profits, while high-discount and high-return segments show signs of profitability risk.

### Business Interpretation

Future growth depends on balancing revenue expansion with profitability and customer satisfaction.

### Recommended Action

Prioritize investment in profitable categories and regions while reducing exposure to loss-making products, excessive discounting, and operational inefficiencies.

---

# Calculated Fields Used

## Profit Margin

Formula:
SUM([Profit]) / SUM([Sales])

Purpose:
Measures the percentage of sales retained as profit.

## Cost

Formula:
[Sales] - [Profit]

Purpose:
Estimates the cost associated with generating sales.

## Average Order Value

Formula:
SUM([Sales]) / COUNTD([Order ID])

Purpose:
Measures average revenue generated per order.

## Return Rate

Formula:
SUM([Return Flag]) / COUNT([Order ID])

Purpose:
Measures the percentage of orders returned.

## Shipping Delay Bucket

Purpose:
Groups delivery times into business-friendly categories for shipping performance analysis.


# ShopNest Store Performance Analysis | Power BI

### 📌 Project Overview

ShopNest is an e-commerce marketplace in Portugal that connects small businesses from different regions with customers. The platform enables merchants to sell products online and ship orders through logistics partners. The project dataset contains anonymized commercial information.

I developed an interactive Power BI dashboard to analyze e-commerce performance across sales, delivery efficiency, customer satisfaction, payment behavior, product categories, and regional trends. The goal was to transform raw data into meaningful insights that support data-driven business decisions.

### 🛠 Tools and Technologies

- **Power BI:** Dashboard development, data modeling, and visualization
- **Power Query:** Data cleaning and transformation
- **DAX:** Measures and key performance indicators (KPIs)
- **Visualizations:** Bar charts, line charts, pie charts, treemaps, maps, and column charts

### 🔍 Key Highlights and My Role

- **Data Cleaning and Transformation:** Cleaned and prepared datasets in Power Query, checked duplicates, handled data types, and prepared tables for analysis.
- **Data Modeling:** Established relationships between Customers, Orders, Order Items, Products, Payments, Reviews, and other relevant tables.
- **DAX Calculations:** Developed measures for sales, delayed orders, average review score, and revenue trends.
- **Dashboard Design:** Created a multi-page dashboard with navigation buttons to make analysis easier.
- **Interactive Visualizations:** Used charts and maps to explore product categories, delivery performance, payment methods, and regional sales.
- **Business Analysis:** Identified sales patterns and delivery delays to develop recommendations for further investigation.

### 📊 Working Demo of Power BI Dashboard:

**Working Demo:**  https://www.awesomescreenshot.com/video/57389210?key=070498d6034ee7be307b5f69493b2e2c


### 📈 Key Business Findings and Recommendations

#### 1. Top Product Categories by Sales

**Finding:** Health & Beauty recorded 1.19M in sales, followed by Watches & Gifts at 1.17M and Sports & Leisure at 0.91M.

**Evidence:** Health & Beauty exceeded Watches & Gifts by 0.02M in the displayed chart.

**Business Recommendation:** Review inventory availability, customer demand, and product profitability in these leading categories before deciding where to allocate additional stock.

**Time Context:** The chart does not specify a date range.

#### 2. Monthly Delivery Delay Analysis

**Finding:** March recorded approximately 1.6K delayed orders, followed by February at 1.1K and November at 1.0K.

**Evidence:** March has the highest displayed delayed-order count among the months shown.

**Business Recommendation:** Investigate delayed orders by seller, customer state, and delivery duration to identify potential causes. Use these results to determine where logistics improvements may be needed.

**Time Context:** The chart displays months, but the year is not specified. These values should not be treated as a recurring seasonal pattern until the year and date coverage are verified.

#### 3. Yearly Revenue Trend

**Finding:** Displayed revenue increased from 5.5M in 2017 to 6.6M in 2018, a difference of 1.1M or approximately 20%.

**Evidence:** The displayed values show an increase between 2017 and 2018.

**Business Recommendation:** Analyze which product categories and states contributed to the increase before making inventory or marketing decisions.

**Time Context:** The chart covers 2016–2018. The 2016 value is displayed as 0.0M and should be validated before drawing conclusions about the full trend.

**Note:** The figures above are transcribed from the dashboard chart labels. Confirm the currency, units, date filters, and underlying measures in Power BI before presenting them as final business results.

### 📌 Key KPIs and DAX Measures

The following are example DAX definitions. Confirm that the formulas match the measures used in your actual Power BI report.

#### Total Sales

```DAX
Total Sales = SUM(order_items[price])
```

Calculates the sum of item prices. This measure does not include freight charges unless they are added separately.

#### Total Payment Value

```DAX
Total Payment Value = SUM(order_payments[payment_value])
```

Calculates the sum of recorded payment values.

#### Average Review Score

```DAX
Average Review Score = AVERAGE(order_reviews[review_score])
```

Calculates the average review score.

#### Delayed Orders

```DAX
Delayed Orders =
CALCULATE(
    COUNT(orders[order_id]),
    FILTER(
        orders,
        orders[order_delivered_customer_date]
            > orders[order_estimated_delivery_date]
    )
)
```

Counts orders delivered after their estimated delivery date. Check how blank delivery dates and undelivered orders are handled in your report.

Other KPIs displayed or analyzed in the project include Total Orders, On-Time Orders, and revenue trends. Include their DAX definitions once you have verified the actual formulas.

### 🧹 Data Cleaning and Data Model

#### Data Preparation

- Checked for duplicate records in relevant key columns.
- Corrected data types for numeric values, dates, and timestamps.
- Prepared related tables for analysis using Power Query.
- Reviewed relationships between the tables used in the dashboard.

#### Main Table Relationships

The model connects the following business entities:

- Customers → Orders → Order Items → Products
- Orders → Payments
- Orders → Reviews
- Order Items → Sellers
- Products → Category Translation

These relationships support analysis of sales, order delivery, product categories, payments, customer reviews, and sellers. Verify the actual relationship cardinalities and filter directions in Power BI Model view before describing the model as a fully optimized star schema.

### 🎯 Key Learnings and Conclusion

This project strengthened my skills in data cleaning, data modeling, DAX calculations, dashboard design, and data storytelling using Power BI.

The dashboard provides an interactive view of e-commerce performance and highlights areas for further investigation, including leading product categories, delivery delays, and changes in yearly revenue. The findings can help guide more detailed analysis of inventory, logistics, and regional sales performance.

The project demonstrates my ability to transform raw business data into visual reports and communicate findings in a structured, business-focused way.

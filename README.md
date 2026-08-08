# E-Commerce-Sales-Data-Analysis
End-to-end E-Commerce Sales data visualization project | Analyzes sales performance, customer purchasing behavior, product trends, payment methods, and order fulfillment metrics using Power BI to support data-driven decision-making.

<img width="1411" height="802" alt="Screenshot 2026-06-04 130552" src="https://github.com/user-attachments/assets/e5d755c8-3c10-43cb-97ae-37047e0d60a4" />

## Table Of Contents

- [Project Overview]
- [Objectives]
- [Dataset Description]
- [DAX Measures]
- [Tools Used]
- [Data Cleaning Process]
- [Key Performance Indicators (KPIs)]
- [Visualizations Created]
- [Key Findings]
- [Business Insights]
- [Strategic Recommendations]
- [Conclusion]
- [Author]

## Project Overview

This project was completed as part of the DecodeLabs Data Analytics Intern Program (Task 4). The objective was to analyze and visualize an E-Commerce dataset to uncover meaningful business insights and communicate findings effectively through interactive dashboards and visual reports. Where I imported my Cleaned datasest, if you have gone through my repos **Task1, 2 & 3** were i performed the basic cleanings and Exploratory Data Analysis(EDA) processes in Excel and queries in SQL, after that i imported the file with Power BI using the **Get Data(Excel workbook)** process to import the datasets, which i have nothing else to clean so i loaded it directly into my Power BI. Then i proceed to Performing all necessary DAX Measures needed for my **Key Performance Indicators (KPIs)**, also proceed in building a dashboard wireframe for my visualisation which came out beautiful with my **Filters (Slicers)** added.   
 
This dashboard presents a holistic view of the company's E-Commerce operations, highlighting sales performance, order fulfillment, customer engagement, product contribution, and marketing channel effectiveness. The business generated over **$1.26M** in revenue, from **1,200** orders, serving **1,189** customers and selling **3,535** units across seven products.


---

## Objectives

* Analyze overall sales performance.
* Identify top-performing products and categories.
* Understand customer purchasing behavior.
* Evaluate order status and fulfillment trends.
* Examine payment method preferences.
* Generate actionable business insights and recommendations through data visualization.

---

## Dataset Description

The dataset contains transactional records from an e-commerce business and includes the following fields:

| Column Name      | Description                      |
| ---------------- | -------------------------------- |
| Order ID         | Unique identifier for each order |
| Date             | Order transaction date           |
| Customer ID      | Unique customer identifier       |
| Product          | Product purchased                |
| Quantity         | Number of units purchased        |
| Unit Price       | Price per unit                   |
| Shipping Address | Delivery location                |
| Payment Method   | Customer payment option          |
| Order Status     | Current status of the order      |
| Tracking Number  | Shipment tracking identifier     |
| Items in Cart    | Number of items added to cart    |
| Coupon Code      | Promotional discount code used   |
| Referral Source  | Source that brought the customer |
| Total Price      | Total order value                |

---
##  DAX Measures:

Average Items per Order = 
     
      AVERAGE(
    'Decodlab Cleaned Data'[ItemsInCart]
      )
      
Average Order Value = 
           
           DIVIDE(
         [Total Revenue],[Total Orders],
         0)
Cancellation Rate = 
     
     DIVIDE(
    [Cancelled Orders],
    [Total Orders],
    0
    )     
Cancelled Orders = 
     
     CALCULATE(
    DISTINCTCOUNT('Decodlab Cleaned Data'[OrderID]),
    'Decodlab Cleaned Data'[OrderStatus] = "Cancelled"
    )
 Completed Orders = 
    
    CALCULATE(
    DISTINCTCOUNT('Decodlab Cleaned Data'[OrderID]),
    'Decodlab Cleaned Data'[OrderStatus] = "Delivered"
    ) 
 Delivered Orders = 
     
     CALCULATE(
    COUNTROWS('Decodlab Cleaned Data'),
    'Decodlab Cleaned Data'[OrderStatus] = "Delivered"
    ) 
Delivery Rate = 
    
    DIVIDE(
    [Delivered Orders],
    [Total Orders],
    0
    ) 
Total Customers = 
    
    DISTINCTCOUNT(
     'Decodlab Cleaned Data'[CustomerID]
    ) 
 Total Orders = 
      
      COUNTROWS(
        'Decodlab Cleaned Data'
        )   
 Total Quantity Sold = 
    
    SUM(
    'Decodlab Cleaned Data'[Quantity]
    )       
Total Revenue = 
    
    SUM(
      'Decodlab Cleaned Data'[TotalPrice]
     )

---

## Tools Used :

* Microsoft Excel (Data Cleaning,EDA)
* SQL (Data Exploration)
* Power BI (Data Visualization)
* GitHub | Linkedln (Project Documentation)

---

## Data Cleaning Process

The following preprocessing steps were performed:

* Removed duplicate records.
* Handled missing values.
* Standardized data formats.
* Verified data consistency.
* Converted date fields into proper date formats.
* Validated numerical fields for analysis.

---

## Key Performance Indicators (KPIs)

The dashboard includes the following KPIs:

* Total Revenue
* Total Orders
* Total Customers
* Average Order Value
* Total Quantity Sold
* Order Delivery Rate

---

## Visualizations Created

### 1. Sales Trend Analysis

* Revenue over time.
* Monthly sales performance.
* Peak and low sales periods.

### 2. Product Performance

* Top-selling products.
* Revenue contribution by product.
* Quantity sold by product.

### 3. Customer Analysis

* Unique customer count.
* Repeat purchase patterns.
* Customer purchasing behavior.

### 4. Payment Method Analysis

* Most preferred payment methods.
* Revenue generated by each payment type.

### 5. Order Status Distribution

* Completed orders.
* Pending orders.
* Cancelled orders.
* Processing orders.

### 6. Referral Source Performance

* Customer acquisition channels.
* Revenue generated by referral sources.

### 7. Coupon Code Analysis

* Coupon usage frequency.
* Impact of discounts on sales.

---

## Key Findings

### 1. Strong Revenue Generation

The business generated **$1.26M** from **1,200** orders.

Average Order Value (AOV) stands at approximately **$1.05K**, indicating relatively high-value purchases / sales performance.

### 2. High Customer Acquisition

The business served **1,189** customers from **1,200** orders.

This suggests most customers placed only one order, indicating an opportunity to improve repeat purchases and customer retention.

### 3. Chair and Printer Products Lead Sales Volume

Top products by quantity sold:

**Chair – 562 units**
**Printer – 542 units**
**Laptop – 535 units**

These products account for a significant portion of total sales volume.

### 4. Revenue is Fairly Distributed Across Products

Top revenue-generating products:

**Chair – $196K**
**Printer – $196K**
**Laptop – $192K**

No single product dominates revenue generation, indicating a well-balanced product portfolio.

### 5. Instagram is the Most Effective Referral Channel

Revenue contribution by referral source:

**Instagram – $275K**
**Email – $262K**
**Google – $250K**
**Facebook – $250K**
**Referral – $227K**

Instagram currently delivers the highest revenue contribution.

### 6. Revenue Peaked Mid-Year

Monthly revenue trend shows:

**Highest month: June ($171K)**
**Lowest month: November ($75K)**

The business experienced significant growth leading into mid-year before declining during the second half.

### 7. Order Status Distribution is Relatively Even

Order statuses are distributed almost equally:

 **Cancelled: 250 orders**
 **Returned: 247 orders**
 **Pending: 237 orders**
 **Shipped: 235 orders**
 **Delivered: 231 orders**

The low proportion of completed deliveries is concerning.

### 8. Delivery Performance Requires Improvement

**Delivery Rate: 19.25%**
**Delivered Orders: 231**

The delivery completion rate is considerably lower than expected for a healthy e-commerce operation.

### 9. Cancellation Rate is High

Overall cancellation rate:

**20.8%**

Some products exceed the overall average:

 **Chair: 25.3%**
 **Laptop: 20.2%**
 **Desk: 20.6%**

## Business Insights

### Sales Performance Insight

The company demonstrates strong revenue performance despite relatively low order fulfillment rates. This suggests that products sold have high average values, helping maintain overall profitability.

### Customer Behavior Insight

The near one-to-one relationship between customers and orders indicates limited customer retention and repeat purchases. Revenue growth is currently driven more by acquisition than customer loyalty.

### Product Performance Insight

Chairs and Printers are the strongest-performing products across both sales volume and revenue. These products represent key revenue drivers and should remain a focus for inventory planning and marketing investments.

### Marketing Channel Insight

Instagram significantly outperforms other referral channels in revenue generation, demonstrating strong customer acquisition effectiveness from social media marketing.

### Operational Efficiency Insight

The high cancellation rate and low delivery rate indicate operational bottlenecks that may exist within:

* Order processing
* Inventory availability
* Logistics coordination
* Last-mile delivery execution

### Seasonal Insight

The substantial revenue spike in June followed by declining sales suggests seasonality or the impact of promotional campaigns. The company may not be sustaining demand effectively after peak periods.

## Strategic Recommendations

### 1. Improve Order Fulfillment Processes

#### Priority: High

 #### Actions:

* Review order processing workflows.
* Improve warehouse efficiency.
* logistics partnerships.
* Track delivery performance using SLA metrics.

#### Expected Outcome:

* Increased delivery rate.
* Reduced customer dissatisfaction.
* Higher customer retention.

## 2. Reduce Product / Order Cancellation Rates

#### Priority: High

#### Focus on:

* Chair
* Laptop
* Desk

#### Actions:

* Investigate root causes of cancellations.
* Improve inventory forecasting.
* Display accurate stock availability.
* Enhance order confirmation procedures.

#### Expected Outcome:

* Lower revenue leakage.
* Improved customer experience.

## 3. Increase Marketing Investment in Instagram

#### Priority: High

#### Actions:

* Expand Instagram advertising campaigns.
* Introduce influencer partnerships.
* Promote best-selling products through targeted campaigns.

#### Expected Outcome:

* Higher customer acquisition.
* Increased revenue generation.

## 4. Launch Customer Retention Programs

#### Priority: Medium

#### Actions:

* Loyalty rewards programs.
* Personalized email marketing.
* Coupon-based repeat purchase incentives.
* Customer membership programs.

#### Expected Outcome:

* Increased repeat purchases.
* Higher customer lifetime value.

## 5. Optimize Product Portfolio Strategy

#### Priority: Medium

#### Actions:

* Prioritize inventory for Chairs, Printers, and Laptops.
* Create bundled offers around top-performing products.
* Promote complementary products.

#### Expected Outcome:

* Increased average order value.
* Improved inventory turnover.

## 6. Address Revenue Decline After June

#### Priority: Medium

#### Actions:

* Analyze successful June campaigns.
* Replicate winning promotions quarterly.
* Introduce seasonal campaigns during low-performing months.

#### Expected Outcome:

* More consistent monthly revenue performance.
* Reduced seasonal fluctuations.

---

## Conclusion

This project demonstrates how data visualization can transform raw e-commerce data into actionable business intelligence. By analyzing sales trends, customer behavior, product performance, and marketing effectiveness, organizations can make informed decisions that drive revenue growth and operational efficiency.

---

### Author

## Clement Eghosa

Data Analyst | Financial Analyst | Business Analyst | Business Intelligence Enthusiast

 **Decodelabs Intern**
 
 * Microsoft Excel
 * Power BI
 * SQL
 * Data Visualization
 * Dashboard Development
 * Business Analytics


[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://linkedin.com/in/eghosa-osalob)
[![GitHub](https://img.shields.io/badge/GitHub-View%20Profile-black?logo=github)](https://github.com/Eghosa-Dataguy)

---
*If you found this project helpful, feel free to ⭐ star the repo or connect on LinkedIn*

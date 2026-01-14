\*\*\* SQL Data Analytics Project – Sales \& Customer Analysis  \*\*\*
\*\* Project Overview \*\*

This project focuses on performing end-to-end data analytics using SQL on a sales dataset to derive meaningful business insights. The analysis covers trend analysis, cumulative metrics, performance comparison, proportional contribution, customer segmentation, and customer reporting using advanced SQL techniques.



\*\* Dataset Information \*\*

* Source: AdventureWorks (Bike Garage) Sample Dataset
* Schema: gold



\*\* Tables used:

* fact\_sales
* dim\_products
* dim\_customers



\*\* Key data domains:

* Sales transactions
* Products and categories
* Customer details
* Order dates and quantities



\*\* Tools \& Technologies \*\*

* SQL (PostgreSQL)
* Window Functions
* CTEs (WITH clause)
* Date \& Time Functions
* Aggregations \& Joins



\*\* Key Analysis Performed \*\*

1️⃣ Change Over Time (Trend Analysis)

Analyzed how sales and customer metrics evolve over time
Identified seasonality and time-based trends

* Grouped data by:
  Year
  Month
  Day of Week
* Techniques used:
  DATE\_TRUNC
  EXTRACT
  Time-based grouping



--Key Business Insight

* &nbsp;2013 had the highest overall sales, quantity, and customer count.
* December 2013 recorded the highest monthly sales.



2️⃣ Cumulative Analysis

* Calculated running totals and cumulative averages
  Evaluated long-term business growth and decline
* Key concepts:
  Window functions with UNBOUNDED PRECEDING
  Year-wise cumulative sales
  Progressive performance tracking



--Key Business Insight:

* Since 2010 and 2014 contain only partial-year data, the real performance should be evaluated from 2011 to 2013.
* 2013 alone contributed more than 55% of total cumulative revenue.
* &nbsp;Although total sales peaked in 2013, the average sales per transaction decreased.

     This may indicate: Increase in transaction volume with smaller order sizes



3️⃣ Performance Analysis

* Compared product performance against:
  Average sales
  Previous year sales
* Identified:
  Above / Below average products
  Year-over-Year (YoY) growth or decline
* Techniques used:
  AVG() OVER (PARTITION BY …)
  LAG() for previous year comparison
  Conditional logic using CASE



--Key Business Insight:

* Across nearly all products, sales increased significantly in 2013 compared to the previous year, indicating a strong expansion phase.
* The sharp YoY increase in 2013 followed by a YoY decrease in 2014 highlights high revenue volatility at the product level.
* Such volatility increases forecasting risk and suggests that growth was not evenly distributed or sustainable across years.



4️⃣ Part-to-Whole (Proportional Analysis)

* Determined category contribution to total sales
  Calculated percentage share of each category
* Key SQL concepts:
  SUM() OVER () for grand totals
  Category-wise contribution
  Percentage calculations using window functions

--Key Business Insight:

* Bikes dominate total revenue, contributing approximately 96.5% of overall sales, making the business heavily dependent on a single product category.
* Accessories (≈2.4%) and Clothing (≈1.2%) contribute marginally to total sales, despite expanding the product portfolio.
* The extreme revenue concentration indicates high category-level risk, where fluctuations in bike sales could significantly impact overall business performance.



5️⃣ Customer Segmentation

* Segmented customers based on:
  Total sales
  Customer lifespan (in months)
* Classified customers into:
  VIP
  Regular
  New
* Approach:
  Aggregated customer-level metrics
  Created custom segments using CASE
  Used date difference logic to calculate customer lifespan



--Key Business Insight:

* New customers dominate the customer base, with 14,828 customers, indicating strong customer acquisition but a relatively short purchasing history for most users.
* Regular customers (2,037) represent a smaller but more established group, suggesting moderate retention beyond the first year.
* VIP customers (1,619) form the smallest segment, yet they contribute disproportionately higher revenue due to higher total spend and longer customer lifespan.



6️⃣ Customer Reporting (View Creation)

* Built a reusable SQL View for customer analytics
  Combined fact and dimension tables
* Generated customer KPIs including:
  Total orders
  Total sales
  Recency
  Average order value
  Average monthly spend
  Age group and customer segment
* Outcome:
  Created a reporting layer that can be directly used for dashboards or further analysis.



--Key Business Insight:

* Identified 4 VIP customers (customer\_keys: 296, 333, 336, 339) who have high historical spending (avg monthly spend > 400) but have not been active for over 155 months.
* These customers represent lost revenue potential despite being historically high-value.

 

📈 Key SQL Concepts Demonstrated

* Common Table Expressions (CTEs)
* Window Functions (OVER, PARTITION BY, ORDER BY)
* Running totals \& cumulative metrics
* Time intelligence using date functions
* Business logic using CASE statements
* View creation for reporting



👤 Author

Pavan Kumar
Aspiring Data Analyst | SQL \& Power BI



\*\* Feedback \*\*

If you find this project useful, feel free to ⭐ the repository or share feedback.



\*\* Acknowledgement \*\*

This project is created for learning and portfolio purposes, inspired by online tutorials and publicly available datasets.




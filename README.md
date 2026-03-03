<h1 align="center"> Crisis Impact Analysis </h1>

### Overview
- **Food delivery businesses** often experience challenges in situations such as food safety incidents, viral social media backlash, or seasonal disruptions such as monsoons. All these can significantly impact customer trust and order volumes.

- **QuickBite Express**, a Bengaluru-based food-tech startup connecting customers with nearby restaurants and cloud kitchens, faced a **major crisis** in June 2025. This report compares **pre-crisis and crisis-period** performance to assess the severity of demand and revenue losses.

- The **goal** of this analysis is to assess the overall impact of the crisis, **identify operational weaknesses**, and generate actionable insights to help **recover lost demand and rebuild customer trust.**

- This **analysis is important** because it supports data-driven decision-making. The insights can help the business **regain market position, improve service reliability, and compete effectively in a highly competitive food delivery industry.**

This project demonstrates end-to-end business analytics, including data cleaning, data modeling, KPI development, DAX calculations, dashboard visualization, crisis impact measurement, and actionable business recommendations.

---

### Business Problem

- QuickBite Express experienced a significant drop in demand and operational performance during the crisis period. The business needed to understand:

  - How severe was the revenue and order decline?

  - Did delivery performance deteriorate?

  - Which cities or vendors were most affected?

  - How did customer sentiment change?

The **objective** was to quantify the crisis impact and identify actionable strategies for recovery.

---

### Table of Contents

- Data Source

- Data Transformation
  
- Data Modeling
  
- DAX Measures

- Tools & Technologies Used 

- Key Insights
  
- Recommendations
  
- Power BI Report
  
- Business Questions

- Acknowledgments

---

### Data Source 

The dataset consists of 4 dimension tables and 4 fact tables.

**Dimension Tables:** dim_customer, dim_delivery_partner, dim_menu_item, and dim_restaurant

**Fact Tables:** fact_orders_actual, fact_order_items, fact_delivery_performance, fact_ratings

Dataset link: [Codebasics](https://codebasics.io/challenges/codebasics-resume-project-challenge/23)

---

### Data Transformation

- Created a Date Dimension table to classify transactions into Pre-crisis and Crisis periods.

- Extracted order_date from order_timestamp in fact_orders to establish a relationship with the Date dimension.

- Identified orphan records in fact_orders that lacked matching customer_id values in dim_customer, which caused blank categories in visuals. Applied an inner join to retain only valid matching records.

- Disabled unused tables to optimize report performance and reduce model size.

---

### Data Modeling

- Designed a **star schema** with fact_orders_actual as the central fact table connected to dimension tables such as customer, restaurant, delivery partner, and date through **many-to-one** relationships.

- Implemented a **one-to-one** relationship between fact_orders_actual and fact_delivery_performance, as both tables operate at the order-level granularity.

- All **relationships** were configured as **active** to ensure accurate filtering and aggregation across metrics.

---

### DAX Measures

- Total Orders – **DISTINCTCOUNT**(order_id)

- Total Revenue – **SUM**(order_amount)

- Average Delivery Time – **AVERAGE**(delivery_time)

- Crisis vs Pre-Crisis Analysis – **CALCULATE()** with date-based filtering

- Ratings Analysis – **AVERAGE**(rating)

- Percentage Change – **DIVIDE()** to handle safe division and avoid errors

---

### Tools & Technologies Used

- Power BI Desktop (Data Modeling & Visualisation)

- Power Query (ETL & Data Transformation)

- DAX (Analytical Calculations)

- Star Schema Data Modeling Concepts

- Power BI Service (Report publishing and sharing)

- CSV Data Source

---

### Key Insights

- **Order cancellation %** increased significantly during the crisis period across all cities, indicating operational disruption at a systemic level.

- **Average delivery time increased** during the crisis, directly impacting customer experience.

- **Customer ratings declined,** with reviews frequently mentioning issues such as cold food and food quality problems.

- **Certain restaurants** experienced **higher order losses** than others, suggesting uneven resilience among vendor partners.

- The crisis impacted customers, delivery performance, and restaurant partners simultaneously.

---

### Recommendations

- **Improve demand forecasting models** during uncertain periods to handle sudden demand fluctuations.

- **Strengthen coordination between restaurants and delivery partners** to reduce cancellations.

- Implement **real-time order tracking** and proactive delay communication to manage customer expectations.

- **Monitor vendor-level performance** more closely to identify quality issues early.

- **Set realistic delivery timelines** during the crisis periods to maintain customer trust.

---

### Power BI Report

The report has 4 pages with a Pre-Crisis and Crisis comparison.

- **Page 1:** Crisis Impact Overview - KPIs (Customers, Orders, Revenue, and Average Order Value), Revenue and Demand trends, City-wise crisis impact comparison table.

- **Page 2:** Operational Breakdown Analysis - KPIs (Order Cancellation %, Average Delivery Time, SLA Breach %, and Average Rating), Rating trend, High-volume vendor performance table, and customer sentiment insights.

- **Page 3:** Recovery Strategies - Actionable insights from the analysis.

- **Page 4:** About - About - Overview, objective, data source, tools used, and analyst profile.

[Check out the report here!](https://tinyurl.com/mt7aphnk)

---

### Business Questions

**1. How severe was the revenue and order decline?**
  
The crisis had a significant financial impact on the business.
Revenue declined by **70.9%**, and total orders declined by **69.8%**, showing a sharp drop in customer demand during the crisis period.

---

**2. Did delivery performance deteriorate?**
  
Yes, delivery performance worsened during the crisis.

**Average delivery time** increased from 39.5 minutes to 60.1 minutes, which is a **52.1% increase.**

**SLA Breach percentage increased** by **55.5%**, indicating that more orders were delivered later than the promised time.

This confirms that operational efficiency was significantly affected.

---

**3. Which cities or vendors were most affected?**
  
The **impact** was largely **systemic** rather than city-specific.
Almost all cities experienced a similar decline in demand.

**High-volume vendors** (with more than 50 orders in the pre-crisis period) saw a severe drop in orders, with many falling to below 10 orders during the crisis.
This indicates that even strong-performing vendors were **heavily affected.**

---

**4. How did customer sentiment change?**
  
Customer sentiment shifted from **positive to negative** during the crisis.

**Before the crisis,** reviews commonly included phrases like **“fresh and delicious,” “excellent service,” and “loved it.”**

**During the crisis,** reviews frequently mentioned **“food quality issues,” “food safety concerns,” and delays.**

This suggests that delivery delays and operational challenges negatively impacted customer satisfaction.

---

### Acknowledgments

Special thanks to **Dhaval Patel Sir, Hemanand Vadivel Sir, and Codebasics** for providing the dataset used in this analysis project.
The dataset enabled hands-on practice in data modeling, transformation, and business analysis.


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

- Tools Used

- Key Insights
  
- Recommendations
  
- Power BI Report
  
- Business Questions
  
- KPIs Tracked
  
- Learning Outcomes

---

### Data Source 

The dataset consists of 4 dimension tables and 4 fact tables.

**Dimension Tables:** dim_customer, dim_delivery_partner, dim_menu_item, and dim_restaurant

**Fact Tables:** fact_orders, fact_order_items, fact_delivery_performance, fact_ratings

Dataset link: [Codebasics](https://codebasics.io/challenges/codebasics-resume-project-challenge/23)

---

### Data Transformation

- Created a Date Dimension table to classify transactions into Pre-crisis and Crisis periods.

- Extracted order_date from order_timestamp in fact_orders to establish relationship with the Date dimension.

- Identified orphan records in fact_orders that lacked matching customer_id values in dim_customer, which caused blank categories in visuals. Applied an inner join to retain only valid matching records.

- Disabled unused tables to optimize report performance and reduce model size.

---

### Data Modeling


# 📊 Atliq Sales Insights – Power BI Dashboard

## 🏢 Business Context
Atliq Computer Hardware Solutions is a pan-India company supplying computer hardware and peripherals such as laptops, desktops, graphics cards, printers, and accessories to multiple retail and distributor clients across India.

The Sales Director faced challenges due to:
- Rapidly changing market dynamics
- Dependence on verbal updates from regional managers
- Fragmented Excel-based reporting
- Lack of a single source of truth for sales performance

---

## ❌ Business Problem
- Overall sales were declining, but leadership lacked clarity on the underlying causes
- Regional insights were subjective and often over-optimistic
- Data existed across multiple Excel files, making analysis slow and error-prone
- No real-time visibility into YoY growth, profitability, or regional performance

---

## ✅ Solution
An **interactive Power BI dashboard** that provides:
- A centralized, data-driven view of business performance
- Real-time KPIs for Revenue, Profit, Expenses, and Quantity
- Market, product, customer, and zone-level insights
- YoY trend analysis to replace verbal forecasting
- Executive-friendly visuals that eliminate reliance on manual reports

---

## 🎯 Success Criteria
- Dashboard reflects the latest available sales data
- Sales team achieves at least **10% cost savings**
- Analysts save **20% of time** previously spent on manual data gathering

---

## 🗂 Dataset Information
Data sourced from a MySQL sales management system maintained by the IT team.  
For simplicity, Power BI is directly connected to the database, although in a production setup a data warehouse would typically be used.

---

## 📌 Data Schema

### Tables Used
- Customers(customer_code, customer_name, customer_type)
- Markets(market_code, market_name, zone)
- Products(product_code, product_name, unit_cost)
- Transactions(transaction_id, product_code, customer_code, market_code, order_date, cost_price, sales_qty, sales_amount, currency)
- Date(dt, year, month, day, month_name, date_yy_mmm)

Initial exploratory analysis was performed in MySQL  
(File: `Exploratory_Analysis/sql_analysis.sql`)

---

## 🔄 Power Query ETL Steps
- Removed transactions with zero sales amount
- Filled missing currency values with INR
- Removed records with missing market codes
- Verified and corrected column data types
- Created derived date columns (Year, Month, Weekday)
- Merged Products and Transactions to fetch cost price
- Removed unnecessary columns

---

## 🧱 Data Model
- Star schema implemented
- Transactions as the fact table
- Customers, Products, Markets, and Date as dimension tables
- One-to-many relationships established

---

## 📊 Key KPIs
- Total Revenue
- Total Expenses
- Total Profit
- Total Quantity Sold
- YoY Sales Growth
- Cost-to-Sales Ratio
- Revenue & Profit by Market, Product, and Customer
- Performance Classification: Moderate, Severe, Critical Decline

---

## 🧠 Key Insights
- Revenue declined **19.6% YoY**, mainly driven by the **West Zone**
- **Laptops and Desktops** are the highest revenue and profit contributors
- **Kochi** emerged as the most resilient market
- **Ahmedabad** identified as the most critical underperforming market
- **TechBazaar (Mumbai)** is the most profitable customer
- Cost-to-Sales Ratio maintained at approximately **81.6%**

---

## 🛠 Tools & Technologies
- SQL
- Power BI
- Power Query
- DAX
- Data Modeling
- Data Visualization

---

## 🚀 Outcome

This dashboard replaced fragmented Excel reporting with a single, interactive analytics solution — enabling Atliq's leadership to identify a **19.6% YoY revenue decline**, isolate **West Zone** as the highest-risk market, and shift from intuition-based decisions to data-driven recovery strategy. Recurring reporting effort reduced by **~20%**.

---

## 📸 Dashboard Preview

### Overview
![Dashboard Overview](Power%20BI/Visuals/dashboard_overview.PNG)

### Profit View
![Profit View](Power%20BI/Visuals/ProfitView.PNG)

### Detailed View
![Detailed View](Power%20BI/Visuals/DetailedView.PNG)

### Glossary
![Glossary](Power%20BI/Visuals/glossary.PNG)

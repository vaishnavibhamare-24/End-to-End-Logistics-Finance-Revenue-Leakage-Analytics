## 📌 Project Overview 

This project simulates a real-world logistics finance analytics use case inspired by last-mile delivery operations (similar to Zipline-style systems).

The objective was to design an end-to-end analytics solution to identify:

Revenue leakage caused by cancelled and failed deliveries

Profit impact across regions and facilities

Operational inefficiencies affecting financial performance

The project combines SQL data modeling with Power BI executive dashboarding to deliver business-ready insights.

## 🎯 Business Problem

In delivery operations:

Cancelled and failed orders still incur operational costs

Revenue is only realized for successfully delivered orders

These failures quietly reduce profit margins

Leadership teams need visibility into:

Where leakage is happening

Why it is happening (cancel vs failure)

How it impacts overall profitability

This project quantifies and visualizes those insights.

## 🛠 Tech Stack

MySQL 8.0

Data modeling

CTEs (Common Table Expressions)

Window functions

Aggregation views

Power BI

KPI dashboards

Interactive slicers

Custom tooltips

Donut & waterfall visual storytelling

Synthetic Logistics Dataset

Designed to simulate realistic operational workflows

## 🧱 Data Model
Tables

1️⃣ orders

Order ID

Region

Facility

Revenue

Promised delivery timestamps

2️⃣ deliveries

Delivery status (Delivered / Cancelled / Failed)

Delivery cost

Cancel reason

3️⃣ delivery_events

Order lifecycle tracking

ORDER_PLACED → PICKED → PACKED → DISPATCHED → DELIVERED

## 📊 Finance Logic Implemented

Revenue realized only for Delivered orders

Cancelled & Failed orders contribute cost without revenue

Profit calculated as:

Delivered → revenue – cost

Cancelled/Failed → negative cost

Leakage cost defined as:

Costs from Cancelled + Failed deliveries

## 🧠 SQL Views Created
🔹 v_finance_fact

Central finance-ready view combining:

Revenue

Delivery cost

Profit

Delivery outcome flags

🔹 v_finance_daily

Daily aggregation including:

Revenue

Profit

Running totals (window functions)

Moving averages

🔹 v_finance_region_rank

Profit ranking by region

Profit share %

🔹 v_finance_leakage_daily

Daily leakage cost

Lost profit

Cumulative leakage trends

## 📈 Power BI Dashboard Features
🔝 Executive KPIs

Total Revenue

Total Leakage Cost

Total Lost Profit

Profit Margin %

## 🌍 Regional Insights

Leakage % of Revenue by Region

Cancellation vs Failure Rate by Region

## 📉 Financial Impact Analysis

Profit Impact by Delivery Status

Leakage Cost Breakdown (Donut)

## 🏭 Operational View

Facility-level Leakage & Profit table

## ⚙ Interactivity

Region slicer

Delivery status slicer

Custom tooltip page displaying:

Cancel Rate %

Failure Rate %

Leakage Cost

##🚦 How to Run the Project
1️⃣ SQL Setup

Run the scripts in this order:

sql/01_schema.sql
sql/02_data_seed.sql
sql/03_views.sql
sql/04_checks.sql

2️⃣ Power BI

Open:

powerbi/Zipline_Finance_Leakage_Dashboard.pbix


Refresh the MySQL connection if required.

##💡 Key Insights from the Analysis

Operational failures directly translate into measurable profit loss

Certain regions show disproportionately high leakage relative to revenue

Delivered orders still carry significant cost impact, requiring cost optimization

Facility-level performance varies, indicating opportunities for operational improvement

## 🏆 What This Project Demonstrates

End-to-end analytics thinking

SQL-based data modeling and transformation

Business KPI design

Financial reasoning

Executive-level dashboard storytelling

Root-cause analysis in logistics operations

👩‍💻 Author

Vaishnavi Bhamare
Master’s in Advanced Data Analytics
University of North Texas

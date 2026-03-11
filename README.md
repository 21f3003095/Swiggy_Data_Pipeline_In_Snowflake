# Food Aggregator Data Pipeline in Snowflake

![Snowflake](https://img.shields.io/badge/Data%20Warehouse-Snowflake-blue)
![SQL](https://img.shields.io/badge/SQL-Analytics-green)
![Streamlit](https://img.shields.io/badge/Dashboard-Streamlit-red)
![Python](https://img.shields.io/badge/Python-3.x-yellow)

A complete **end-to-end analytics pipeline** designed to analyze food delivery revenue data similar to **Swiggy**.

The project demonstrates **modern data warehouse architecture**, dimensional modeling, and an interactive analytics dashboard built on top of **Snowflake**.

The pipeline transforms raw transactional data into meaningful business insights using **SQL-based transformations and analytical modeling**.

---

# Data Flow Architecture

The project follows a layered **modern data warehouse architecture**.

Raw Data → Data Cleaning → Analytics Modeling → Dashboard

![Architecture](Docs/Img/Workflow.jpg)

### Architecture Layers

**Stage Layer**
- Raw CSV ingestion
- Source of truth storage
- No transformation

**Clean Layer**
- Data cleaning
- Standardization
- Entity relationship preparation

**Consumption Layer**
- Dimensional modeling
- Star schema implementation

**Analytics Layer**
- KPI views
- Business metrics
- Dashboard data source

---

# Data Model (ER Diagram)

The following Entity Relationship Diagram represents the logical structure of the data warehouse, including relationships between entities such as customers, restaurants, orders, and delivery agents.

<p align="center">
  <img src="Docs/ERdiagram.svg" width="100%">
</p>


# Data Warehouse Modeling

The analytics model follows a **Star Schema** optimized for high-performance analytical queries.

### Fact Table

`ORDER_ITEM_FACT`

Stores transactional order data.

Key measures include:

- Order revenue
- Quantity
- Order date
- Restaurant reference
- Customer reference
- Delivery agent reference

---

### Dimension Tables

- `MENU_DIM`
- `CUSTOMER_DIM`
- `RESTAURANT_DIM`
- `RESTAURANT_LOCATION_DIM`
- `CUSTOMER_DIM`
- `CUSTOMER_ADDRESS_DIM`
- `DELIVERY_AGENT_DIM`
- `DATE_DIM`

These dimensions provide descriptive attributes used for slicing and aggregating metrics.

---

# Data Lineage

The diagram below shows how data flows across the warehouse layers.

Raw Tables → Clean Tables → Dimension Tables → Fact Table → KPI Views

![Data Lineage](Docs/Img/Order_fact_data_lineage.png)

Example pipeline flow:
CSV_STG
→
Clean Layer Tables
→
Dimension Tables
→
ORDER_ITEM_FACT
→
VW_DAILY_REVENUE_KPIS


This ensures **traceability and transparency** across the entire data pipeline.

---

# Analytics Dashboard

The project includes an **interactive revenue analytics dashboard** built using Streamlit.

The dashboard provides business users with key revenue insights across different time periods.

---

## Revenue Dashboard (2023/2024)

## Dashboard Preview

<p align="center">
  <img src="Docs/Img/dashboard 2023-1.png" width="45%">
  <img src="Docs/Img/dashboard 2023-2.png" width="45%">
</p>

<p align="center">
  <img src="Docs/Img/dashboard 2024-1.png" width="45%">
  <img src="Docs/Img/dashboard 2024-2.png" width="45%">
</p>

Metrics displayed:

- Total Revenue
- Total Orders
- Average Revenue Per Order
- Average Revenue Per Item
- Maximum Order Value

Features include:

- Year selection
- KPI comparison
- Monthly revenue trends
- Growth indicators
- Revenue distribution insights

---

# Business Insights Enabled

The analytics layer enables multiple types of business analysis.

### Revenue Analytics

- Total Revenue
- Average Revenue Per Order
- Average Revenue Per Item

### Performance Analytics

- Top Performing Restaurant
- Delivery Agent Performance

### Trend Analysis

- Revenue Trends Over Time
- Monthly Revenue Growth

### Customer Insights

- Revenue by Customer Segment

### Geographic Analytics

- Revenue by Restaurant & Location
- Geographic Revenue Distribution

These insights support **data-driven decision making for business operations and growth strategy**.

---

# Technology Stack

| Layer | Technology |
|------|------|
| Data Warehouse | Snowflake |
| Data Modeling | Star Schema |
| Data Transformation | SQL |
| Analytics Layer | KPI Views |
| Dashboard | Streamlit |
| Programming | Python |
| Data Source | CSV |

---



## Project Structure

```text
swiggy-revenue-analytics/
│
├── sql/
│   ├── 01 Create DB + Schema.sql
│   ├── 02 Restaurant Entity.sql
│   ├── 03 Location Entity.sql
│   ├── 04 Customer Entity.sql
│   ├── 05 Customer Address Entity.sql
│   ├── 06 Menu Entity.sql
│   ├── 07 Delivery Agent.sql
│   ├── 08 Delivery Entity.sql
│   ├── 09 Order Entity.sql
│   ├── 10 Order Item Entity.sql
│   ├── 11 Date Dim.sql
│   ├── 12 Order Item Fact.sql
│   └── 13 KPI Views.sql
│
├── dashboard/
│   └── streamlit_app.py
│
├── docs/
│   └── images/
│       ├── Workflow.jpg
│       ├── Order_fact_data_lineage.png
│       ├── dashboard_2023_1.png
│       ├── dashboard_2023_2.png
│       ├── dashboard_2024_1.png
│       └── dashboard_2024_2.png
│
└── README.md
```

# Key Capabilities Demonstrated

This project demonstrates core skills in:

### Data Engineering
- Data pipeline architecture
- Data warehouse design
- SQL transformations

### Analytics Engineering
- Star schema modeling
- Fact and dimension design
- KPI semantic layer

### Data Analytics
- Revenue metrics
- Trend analysis
- Business intelligence modeling

### Data Visualization
- Interactive dashboards
- KPI monitoring
- Business insights presentation


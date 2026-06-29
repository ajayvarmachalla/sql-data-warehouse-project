# 📊 Data Warehouse and Analytics Project

Welcome to the **Data Warehouse and Analytics Project** repository! 🚀

This project demonstrates a comprehensive data warehousing and analytics solution, from building a modern data warehouse to generating actionable business insights. Designed as a portfolio project, it highlights industry best practices in **data engineering**, **data warehousing**, and **analytics**.

---

# 📖 Project Overview

This project involves:

1. **Data Architecture:** Designing a modern data warehouse using the **Medallion Architecture** (**Bronze, Silver, and Gold** layers).

2. **ETL Pipelines:** Extracting, transforming, and loading data from source systems into the data warehouse.

3. **Data Modeling:** Developing fact and dimension tables optimized for analytical queries.

4. **Analytics & Reporting:** Creating SQL-based reports and dashboards to deliver actionable business insights.

---

# 🏗️ Project Architecture

The project follows the **Medallion Architecture**, organizing data into Bronze, Silver, and Gold layers to ensure scalable, maintainable, and analytics-ready data processing.

<p align="center">
  <img src="docs/architecture.drawio.png" alt="Data Warehouse Architecture" width="900">
</p>

### Architecture Overview

* **Bronze Layer:** Stores raw ERP and CRM data exactly as received from the source systems.
* **Silver Layer:** Cleanses, validates, standardizes, and integrates the raw data.
* **Gold Layer:** Creates business-ready dimension and fact tables using a **Star Schema** for reporting and analytics.

---

## 🚀 Project Requirements

### Building the Data Warehouse (Data Engineering)

#### Objective

Develop a modern data warehouse using **SQL Server** to consolidate sales data, enabling analytical reporting and informed decision-making.

#### Specifications

* **Data Sources:** Import data from two source systems (**ERP** and **CRM**) provided as CSV files.
* **Data Quality:** Cleanse and resolve data quality issues before analysis.
* **Integration:** Combine both source systems into a single, user-friendly data model optimized for analytical queries.
* **Scope:** Focus only on the latest available data. Historical tracking (historization) is not required.
* **Documentation:** Create clear documentation of the data model to support business stakeholders and analytics teams.

---

## 📊 BI: Analytics & Reporting (Data Analytics)

### Objective

Develop SQL-based analytics to provide valuable business insights into:

* Customer Behavior
* Product Performance
* Sales Trends

These insights empower stakeholders with key business metrics, enabling strategic and data-driven decision-making.

---

## 🎯 Skills Demonstrated

This project demonstrates practical experience in:

* SQL Development
* Data Architecture
* Data Engineering
* ETL Pipeline Development
* Data Warehousing
* Data Modeling
* Data Quality Management
* Business Intelligence (BI)
* Data Analytics
* Reporting & Dashboarding

---

## 🛠️ Technologies Used

* Microsoft SQL Server
* T-SQL
* SQL Server Management Studio (SSMS)
* CSV Data Sources
* Git & GitHub
* Medallion Architecture
* Star Schema
* ETL Processes

---

## 📂 Data Warehouse Components

### Bronze Layer

* Raw CRM Data
* Raw ERP Data

### Silver Layer

* Cleaned CRM Tables
* Cleaned ERP Tables
* Data Quality Checks
* Standardized Business Rules

### Gold Layer

* `gold.dim_customers`
* `gold.dim_products`
* `gold.fact_sales`

The Gold Layer follows a **Star Schema** design using surrogate keys to improve analytical performance and simplify reporting.

---

## 🛡️ License

This project is licensed under the **MIT License**.

You are free to use, modify, and share this project with proper attribution.

---

## 👨‍💻 About Me

Hi there! I'm **Challa Ajay Varma**, currently pursuing a **Master of Data Science** at **RMIT University**, Melbourne, Australia.

I am passionate about:

* Data Science
* Data Engineering
* Machine Learning
* SQL
* Data Warehousing
* Business Analytics

Through academic projects and hands-on learning, I enjoy building data-driven solutions that transform raw data into meaningful insights.

This project showcases my skills in:

* Data Warehousing
* SQL Development
* Data Modeling
* ETL Processes
* Data Quality Management
* Business Analytics

I am continuously expanding my knowledge in data engineering and analytics while working toward a career as a **Data Scientist** or **Data Engineer**.

Thank you for visiting my project repository. I hope you find it useful and insightful.

---



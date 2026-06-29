# 📚 Data Dictionary for Gold Layer

## Overview

The **Gold Layer** is the business-level data representation of the data warehouse, designed to support analytical reporting and business intelligence. It consists of **dimension tables** and **fact tables** that provide clean, business-ready data.

---

# 1. gold.dim_customers

**Purpose**

Stores customer details enriched with demographic and geographic information.

## Columns

| Column Name | Data Type | Description |
|--------------|-----------|-------------|
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| customer_id | INT | Unique numerical identifier assigned to each customer. |
| customer_number | NVARCHAR(50) | Alphanumeric customer identifier used for tracking and referencing. |
| first_name | NVARCHAR(50) | Customer's first name. |
| last_name | NVARCHAR(50) | Customer's last name. |
| country | NVARCHAR(50) | Customer's country of residence. |
| marital_status | NVARCHAR(50) | Customer's marital status (e.g., Married, Single). |
| gender | NVARCHAR(50) | Customer's gender (Male, Female, n/a). |
| birthdate | DATE | Customer's date of birth. |
| create_date | DATE | Date the customer record was created in the CRM system. |

---

# 2. gold.dim_products

**Purpose**

Provides product information and attributes.

## Columns

| Column Name | Data Type | Description |
|--------------|-----------|-------------|
| product_key | INT | Surrogate key uniquely identifying each product record. |
| product_id | INT | Product identifier from the source system. |
| product_number | NVARCHAR(50) | Product code used for inventory and tracking. |
| product_name | NVARCHAR(50) | Product name. |
| category_id | NVARCHAR(50) | Product category identifier. |
| category | NVARCHAR(50) | Product category (e.g., Bikes, Components). |
| subcategory | NVARCHAR(50) | Product subcategory. |
| maintenance_required | NVARCHAR(50) | Indicates whether maintenance is required (Yes/No). |
| cost | INT | Product cost. |
| product_line | NVARCHAR(50) | Product line or series (e.g., Road, Mountain). |
| start_date | DATE | Date the product became available. |

---

# 3. gold.fact_sales

**Purpose**

Stores transactional sales data for analytical reporting.

## Columns

| Column Name | Data Type | Description |
|--------------|-----------|-------------|
| order_number | NVARCHAR(50) | Sales order number (e.g., SO54496). |
| product_key | INT | Surrogate key referencing **gold.dim_products**. |
| customer_key | INT | Surrogate key referencing **gold.dim_customers**. |
| order_date | DATE | Date the order was placed. |
| shipping_date | DATE | Date the order was shipped. |
| due_date | DATE | Date payment was due. |
| sales_amount | INT | Total sales amount for the order line. |
| quantity | INT | Quantity ordered. |
| price | INT | Unit price of the product. |

---

# Star Schema

```
                    +----------------------+
                    | gold.dim_customers   |
                    |----------------------|
                    | customer_key (PK)    |
                    +----------+-----------+
                               |
                               |
                               |
+----------------------+       |       +----------------------+
| gold.dim_products    |       |       | gold.fact_sales      |
|----------------------|       |       |----------------------|
| product_key (PK)     |-------+-------| product_key (FK)     |
+----------------------+               | customer_key (FK)    |
                                       | order_number         |
                                       | order_date           |
                                       | shipping_date        |
                                       | due_date             |
                                       | quantity             |
                                       | price                |
                                       | sales_amount         |
                                       +----------------------+
```

---

# Surrogate Keys

The Gold Layer uses **surrogate keys** instead of business keys.

Example:

| customer_key | customer_id | first_name |
|--------------|-------------|------------|
| 1 | 11000 | Jon |
| 2 | 11001 | Eugene |

The **fact table** stores `customer_key` instead of `customer_id`.

This approach:

- Improves join performance
- Keeps relationships stable if source system IDs change
- Supports historical data management
- Follows dimensional modeling best practices

---

# Gold Layer Summary

| Table | Description |
|--------|-------------|
| gold.dim_customers | Customer dimension containing demographic information. |
| gold.dim_products | Product dimension containing product attributes. |
| gold.fact_sales | Fact table containing sales transactions. |

---

## Technologies Used

- SQL Server 2022
- T-SQL
- Data Warehouse (Bronze → Silver → Gold)
- Star Schema
- Dimensional Modeling

---

**Author:** Ajay Challa  
**University:** RMIT University  
**Project:** SQL Data Warehouse Project

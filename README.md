# Power BI PR3 — Olist E-Commerce Data Model

## Project Overview
This project builds a star schema data model in Power BI using the Brazilian
E-Commerce Public Dataset by Olist from Kaggle.

## Dataset
-**Name:** Brazilian E-Commerce Public Dataset by Olist
-**Author:** Olist (olistbr)
-**Kaggle URL:** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
-**Files:** 9 CSV files
-**Rows:** ~99,441 orders, ~112,650 order items

## Star Schema Diagram
(Add your hand-drawn or screenshotted star schema here)

## Fact Tables
-FactOrderItems (112,650 rows)
-FactPayments (103,886 rows)
-FactReviews (99,224 rows)

## Dimension Tables
-DimOrders (99,441 rows)
-DimCustomers (99,441 rows)
-DimProducts (32,951 rows)
-DimSellers (3,095 rows)
-DimDate (1,096 rows)

## Relationships (7 Active)
| From | To | Column | Cardinality | Filter |
| :--- | :--- | :--- | :--- | :--- |
| FactOrderItems | DimOrders | order_id | *:1 | Single |
| FactOrderItems | DimProducts | product_id | *:1 | Single |
| FactOrderItems | DimSellers | seller_id | *:1 | Single |
| DimOrders | DimCustomers | customer_id | *:1 | Single |
| DimDate | DimOrders | order_purchase_timestamp | 1:* | Single |
| FactPayments | DimOrders | order_id | *:1 | Single |
| FactReviews | DimOrders | order_id | *:1 | Single |

## Inactive Relationships (1)
-DimDate → DimOrders[order_delivered_customer_date]

## Hierarchies
-Date Hierarchy: Year → Quarter → Month_Name
-Product Hierarchy: Product_Category_EN → product_id
-Seller Location: seller_state → seller_city
-Customer Location: customer_state → customer_city

## Tools Used
-Power BI Desktop
-Power Query (for DimDate creation and product category merge)

## Screenshots
(Add screenshots of Model View and all 3 report pages)

## Video Link
(Add your video link here)

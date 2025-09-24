# ZEPTO_SQL_DATA_ANALYSIS_PROJECT
🛒 Zepto E-commerce SQL Data Analyst Portfolio Project
This is a complete, real-world data analyst portfolio project based on an e-commerce inventory dataset scraped from Zepto — one of India’s fastest-growing quick-commerce startups. This project simulates real analyst workflows, from raw data exploration to business-focused data analysis.

This project is perfect for:
📊 Data Analyst aspirants who want to build a strong Portfolio Project for interviews and LinkedIn

📌 Project Overview
The goal is to simulate how actual data analysts in the e-commerce or retail industries work behind the scenes to use SQL to:

✅ Set up a messy, real-world e-commerce inventory database

✅ Perform Exploratory Data Analysis (EDA) to explore product categories, availability, and pricing inconsistencies

✅ Implement Data Cleaning to handle null values, remove invalid entries, and convert pricing from paise to rupees

✅ Write business-driven SQL queries to derive insights around pricing, inventory, stock availability, revenue and more

📁 Dataset Overview
The dataset was sourced from Kaggle and was originally scraped from Zepto’s official product listings. It mimics what you’d typically encounter in a real-world e-commerce inventory system.

Each row represents a unique ID for a product. Duplicate product names exist because the same product may appear multiple times in different package sizes, weights, discounts, or categories to improve visibility – exactly how real catalog data looks.

🧾 Columns:

Z_id: Unique identifier for each product entry (Primary Key)

name: Product name as it appears on the app

category: Product category like Fruits, Snacks, Beverages, etc.

mrp: Maximum Retail Price (originally in paise, converted to ₹)

discountPercent: Discount applied on MRP

discountedSellingPrice: Final price after discount (also converted to ₹)

availableQuantity: Units available in inventory

weightInGms: Product weight in grams

outOfStock: Boolean flag indicating stock availability

quantity: Number of units per package (mixed with grams for loose produce)

🔧 Project Workflow
Here’s a step-by-step breakdown of what we do in this project:

1. Database & Table Creation
We start by creating a SQL table with appropriate data types:

CREATE TABLE ZEPTO (
    Z_ID INT AUTO_INCREMENT PRIMARY KEY,
    CATEGORY VARCHAR(150),
    NAME VARCHAR(150) NOT NULL,
    MRP DECIMAL(8,2),
    DISCOUNTPERCENT DECIMAL(5,2),
    AVAILABLEQUANTITY INT,
    DISCOUNTEDSELLINGPRICE DECIMAL(8,2),
    WEIGHTINGMS INT,
    OUTOFSTOCK VARCHAR(10),   -- Stores 'True' / 'False' directly from CSV
    QUANTITY INT
);
2. Data Import
Loaded CSV using import feature.

3. 🔍 Data Exploration
Counted the total number of records in the dataset

Viewed a sample of the dataset to understand structure and content

Checked for null values across all columns

Identified distinct product categories available in the dataset

Compared in-stock vs out-of-stock product counts

Detected products present multiple times, representing different SKUs

4. 🧹 Data Cleaning
Identified and removed rows where MRP or discounted selling price was zero

Converted mrp and discountedSellingPrice from paise to rupees for consistency and readability

5. 📊 Business Insights
Found top 10 best-value products based on discount percentage

Identified high-MRP products that are currently out of stock

Estimated potential revenue for each product category

Filtered expensive products (MRP > ₹500) with minimal discount

Ranked top 5 categories offering highest average discounts

Calculated price per gram to identify value-for-money products

Grouped products based on weight into Low, Medium, and Bulk categories

Measured total inventory weight per product category

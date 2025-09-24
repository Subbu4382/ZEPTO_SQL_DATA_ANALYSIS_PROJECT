# 🛒 ZEPTO SQL DATA ANALYSIS PROJECT  

**Zepto E-commerce SQL Data Analyst Portfolio Project**  

This is a **complete, real-world Data Analyst Portfolio Project** based on an **e-commerce inventory dataset scraped from Zepto** — one of India’s fastest-growing quick-commerce startups.  

It simulates real analyst workflows, from **raw data exploration** to **business-focused data analysis**.  

---

## 🎯 Perfect For
- 📊 **Data Analyst aspirants** who want to build a **strong Portfolio Project** for interviews and LinkedIn.  

---

## 📌 Project Overview  
The goal is to simulate how actual **data analysts in e-commerce/retail industries** work behind the scenes using SQL to:  

✅ **Set up** a messy, real-world e-commerce inventory database.  
✅ Perform **Exploratory Data Analysis (EDA)** to explore product categories, availability, and pricing inconsistencies.  
✅ Implement **Data Cleaning** to handle null values, remove invalid entries, and convert pricing from paise to rupees.  
✅ Write **business-driven SQL queries** to derive insights around pricing, inventory, stock availability, revenue, and more.  

---

## 📁 Dataset Overview  
The dataset was sourced from **Kaggle** and scraped from Zepto’s official product listings.  
It mimics real-world **e-commerce inventory systems**.  

- Each row = **unique product entry**.  
- Duplicate product names exist because the same product may appear multiple times in **different sizes, weights, discounts, or categories**.  
- This reflects real catalog data.  

---

### 🧾 Columns in Dataset
- **Z_id** → Unique identifier for each product entry *(Primary Key)*  
- **name** → Product name as shown on app  
- **category** → Product category (Fruits, Snacks, Beverages, etc.)  
- **mrp** → Maximum Retail Price *(originally in paise, converted to ₹)*  
- **discountPercent** → Discount applied on MRP  
- **discountedSellingPrice** → Final selling price after discount *(converted to ₹)*  
- **availableQuantity** → Units available in inventory  
- **weightInGms** → Product weight in grams  
- **outOfStock** → Boolean flag *(‘True’ / ‘False’)*  
- **quantity** → Number of units per package *(mixed with grams for loose produce)*  

---

## 🔧 Project Workflow  

### **1️⃣ Database & Table Creation**
Created SQL table with appropriate datatypes:  

```sql
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

2️⃣ Data Import
Loaded CSV dataset using MySQL import feature.

3️⃣ 🔍 Data Exploration

  -- Counted total number of records in dataset.

  -- Viewed sample records to understand structure.

  -- Checked for null values across all columns.

  --Identified distinct product categories.

  -- Compared in-stock vs out-of-stock products.

  -- Detected duplicate products (SKUs).

4️⃣ 🧹 Data Cleaning

Removed rows with zero MRP or discounted price.

Converted prices from paise → rupees for readability.

5️⃣ 📊 Business Insights

🏷 Found Top 10 best-value products by discount percentage.

❌ Identified high-MRP products currently out of stock.

💰 Estimated potential revenue per category.

🔎 Filtered expensive products (MRP > ₹500) with minimal discounts.

📉 Ranked Top 5 categories offering highest average discounts.

⚖ Calculated price per gram for value-for-money products.

📦 Grouped products by weight → Low, Medium, Bulk categories.

🏋️ Measured total inventory weight per category.

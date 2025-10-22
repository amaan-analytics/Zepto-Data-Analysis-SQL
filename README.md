# 🛒 Zepto E-commerce Product and Inventory Analysis (SQL)

## 🌟 Project Overview: Maximizing Retail Efficiency

This project leverages advanced SQL techniques to conduct a deep-dive analysis of an e-commerce product and inventory dataset (simulating Zepto operations). The primary objective was to move beyond simple data retrieval and deliver **actionable business intelligence** across core operational areas: pricing, stock management, and logistics.

**Key Skills Demonstrated:** Advanced SQL, Data Cleaning, Retail Analytics, Business Intelligence.

---

## 🎯 Problem Statement & Project Goal

### Problem Statement
How can a rapid-delivery retailer like Zepto optimize pricing strategies and inventory management to maximize estimated revenue and ensure operational efficiency, given raw product and stock data?

### Project Goal
To use SQL to clean the raw data and generate eight specific, measurable insights that directly inform decisions for the Inventory, Marketing, and Logistics teams.

---

## 🛠️ Methodology and Technical Stack

* **Database:** PostgreSQL
* **Language:** SQL
* **Core Methodologies:**
    * Data Quality Check (Handling nulls and duplicates).
    * Data Normalization (Price unit conversion).
    * Comparative Analysis (Discounts vs. MRP).
    * Unit Economics (`price_per_gram`).

### Data Cleaning and Preparation

A crucial step was performed to ensure the integrity of financial analysis:
1.  [cite_start]**Price Correction:** Removed products with invalid zero prices (`mrp = 0`)[cite: 105, 106].
2.  [cite_start]**Unit Conversion:** Normalized all financial columns (`mrp` and `discountedSellingPrice`) from **Paise to Rupees** by dividing by 100.0[cite: 108, 109, 110].

---

## 📈 Key Findings and Analysis

The analysis was structured around answering 8 strategic business questions:

| Area | Insight Generated | SQL Query Concept | Business Impact |
| :--- | :--- | :--- | :--- |
| **Revenue** | [cite_start]**Estimated Total Revenue Per Category** [cite: 121] | [cite_start]`SUM(Price * AvailableQuantity)` [cite: 122] | Identifies high-value categories for investment. |
| **Profit** | [cite_start]Products with **High MRP (>$500) and Low Discount (<10%)**[cite: 125]. | [cite_start]`WHERE MRP > 500 AND Discount < 10` [cite: 127, 129] | Pinpoints critical, high-margin, full-price items. |
| **Inventory** | [cite_start]**High-MRP Products that are Out-of-Stock**[cite: 117]. | [cite_start]`WHERE OutofStock = 'True' AND MRP > 300` [cite: 119] | Flags immediate priorities to recover potential lost sales. |
| **Pricing** | [cite_start]**Top 5 Categories by Average Discount**[cite: 131]. | [cite_start]`AVG(DiscountPercent) DESC LIMIT 5` [cite: 132, 135] | Guides pricing policy and margin control efforts. |
| **Value** | [cite_start]**Price Per Gram (Unit Cost)** for products over 100g[cite: 136]. | [cite_start]`ROUND(Price / WeightInGms)` [cite: 138] | Assesses true product value for marketing and competitive analysis. |
| **Logistics** | [cite_start]**Total Inventory Weight Per Category**[cite: 149]. | [cite_start]`SUM(WeightInGms * AvailableQuantity)` [cite: 150] | Essential data for warehouse capacity and shipping cost models. |

---

## ✅ Actionable Recommendations

Based on the derived insights, the following recommendations are put forth:

1.  **Inventory Prioritization:** Immediately prioritize restocking the identified **High-MRP, Out-of-Stock** items to minimize high-value revenue loss (based on Q2).
2.  **Marketing Focus:** Create targeted campaigns promoting the products with the lowest **Price Per Gram** (Q6) and the **High-MRP, Low-Discount** items (Q4) to attract value-conscious customers and maximize profitability, respectively.
3.  **Margin Review:** Investigate the pricing strategies within the **Top 5 categories with the Highest Average Discount** (Q5) to determine if margins can be safely increased without impacting sales volume.

---

## 📁 Repository Contents

The full SQL script, containing all data cleaning and analysis queries, can be found in the file: **`zepto Data Analysis project.sql`**

---
*Connect with me on LinkedIn: [[LinkedIn Profile Link](https://www.linkedin.com/in/amaan-ul-haq-33bbaa380/)]*

*Created by: `amaan_analytics`*

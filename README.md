# 📊 Retail Sales & Profitability Analytics

An end-to-end **Microsoft Excel** data analysis and business intelligence project evaluating **9,977 US retail transactions** ($2.30M total revenue) to uncover product, regional, and discounting drivers behind profit margins.

---

## 📌 Project Overview

Retailers often generate high top-line revenue while quietly losing money on heavily discounted orders or bulky fulfillment categories. This project transforms raw Superstore transaction logs into a structured, 6-sheet Excel analytics model and dual interactive dashboards to answer:
* Which categories, sub-categories, and regions drive true profitability vs. empty revenue?
* How severely does discounting erode overall profit margins?
* Where are the biggest operational profit leaks, and how can pricing rules fix them?

---

## 🛠️ Excel Architecture & Workflow

The workbook (`Retail_sales_Analytics.xlsx`) is organized into **6 structured sheets**:

1. **Data Sourcing & Profiling (`Raw_Data`):** Imported 9,994 raw US Superstore records across 13 attributes (shipping mode, customer segment, geography, product hierarchy, sales, quantity, discount, and profit).
2. **Data Cleaning & Structuring (`Clean_data`):**
   * Identified and removed **17 exact duplicate rows** (9,994 → 9,977 unique transactions, zero null values).
   * Converted the cleaned range (`A1:M9978`) into a dynamic named Excel Table (`salesdata`) so formulas and PivotTables auto-expand on refresh.
3. **Pivot Modeling (`analysis`):** Built **7 dynamic PivotTables** and 3 embedded comparison charts slicing performance across Category, Sub-Category, Region, Top 5 States, Customer Segment, Ship Mode, and Discount tiers.
4. **Dual Interactive Dashboards (`Dashboard` & `Dashboard2`):**
   * **Executive KPI Cards:** Driven by dynamic structured references (`SUM(salesdata[Sales])`, `SUM(salesdata[Profit])`, `SUM(salesdata[Quantity])`, and `AVERAGE(salesdata[Discount])`).
   * **Two-Canvas Layout:** Separates 3 core executive BarCharts on `Dashboard` from 4 deep-dive BarCharts on `Dashboard2` to prevent visual clutter.
   * **Cross-Filtering Slicers:** 3 connected slicers (**Region**, **Category**, and **Segment**) enable instant ad-hoc filtering across visuals.

---

## 📈 Headline KPIs

| Metric | Value | Notes |
| :--- | :--- | :--- |
| **Total Sales** | **$2,296,195.59** | Across 9,977 clean orders ($230.15 AOV) |
| **Total Profit** | **$286,241.42** | **12.47%** overall profit margin |
| **Total Units Sold** | **37,820** | Spanning 17 product sub-categories |
| **Average Discount** | **15.63%** | Primary driver of margin erosion |

---

## 🔍 Key Analytical Insights

* **The Discount Profitability Cliff:**
  * **4,787 zero-discount orders** generated **$320.8K in profit** (**29.51% margin**).
  * **5,190 discounted orders** resulted in a net loss of **-$34.6K** (**-2.86% margin**).
* **Category Performance:**
  * **Technology** leads both revenue and profit (**$145.5K profit**, **17.4% margin**), followed closely by **Office Supplies** (**$122.4K profit**, **17.0% margin**).
  * **Furniture** generates high volume but yields only **$18.4K profit** (**2.5% margin**), dragged down heavily by **Tables** (**-$17.7K loss** on $207.0K sales) and **Bookcases** (**-$3.5K loss**).
* **Regional & State Outliers:**
  * **West** leads all regions ($725.3K sales, $108.3K profit, **14.9% margin**), followed by **East** ($678.4K sales, $91.5K profit, **13.5% margin**).
  * **Central** lags with the lowest margin (**7.9%**), heavily impacted by steep losses in **Texas (-$25.8K)**, alongside **Pennsylvania (-$15.6K)** in the East.
* **Customer Segment & Operations:**
  * **Consumer** drives **50.6%** of total revenue ($1,160.8K sales, $134.0K profit), ahead of Corporate ($706.1K) and Home Office ($429.3K).
  * **Standard Class** accounts for **60.2%** of all units shipped (22,756 units, $164.0K profit).

---

## 💡 Strategic Recommendations

1. **Scale High-Margin Winners:** Prioritize inventory and marketing behind **Phones** ($44.5K profit) and **Binders** ($30.2K profit) where margins consistently exceed 13–17%.
2. **Cap Deep Discounting on Bulky Furniture:** Audit discount thresholds on **Tables** and **Bookcases** to eliminate negative-margin orders and high shipping drag.
3. **Regional Pricing Recovery:** Replicate West and East discounting controls in underperforming high-volume states like **Texas** and **Pennsylvania**.

---

## 📂 Repository Contents

* `Retail_sales_Analytics.xlsx` — Complete 6-sheet Excel workbook with cleaned table (`salesdata`), 7 PivotTables, KPI cards, and interactive dashboards.
* `Retail_Sales_Analytics_Presentation.pptx` — 11-slide executive presentation summarizing methodology, visuals, and business recommendations.

---

## 👤 Author

**Parikshit Kapasiya**  
* [LinkedIn](https://www.linkedin.com/in/parikshit-kapasiya)  
* Email: `parikshitkapasiya@gmail.com`
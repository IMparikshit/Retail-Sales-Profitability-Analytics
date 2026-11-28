# 📊 Retail Sales & Profitability Analytics

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Data Analytics](https://img.shields.io/badge/Data_Analytics-00599C?style=for-the-badge&logo=chartdotjs&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## 📌 Project Overview
An end-to-end **Retail Sales & Profitability Analytics** solution built in Microsoft Excel using the US Superstore dataset. This project transforms raw transactional logs into an automated, interactive, multi-dashboard business intelligence tool designed to identify revenue drivers, uncover margin erosion caused by heavy discounting, and provide actionable recommendations for regional and product-level profitability.

---

## 📂 Repository Structure
```text
├── Raw_data_retail_sales.xlsx              # Original unformatted dataset (9,994 rows × 13 columns)
├── clean_data.xlsx                         # Deduplicated and structured dataset (9,977 unique rows)
├── Retail_sales_Analytics.xlsx             # Full 6-sheet Excel workbook (Data, Pivots, Dual Dashboards)
├── Retail_Sales_Analytics_Presentation.pptx # Executive stakeholder presentation deck
└── README.md                               # Project documentation
```

---

## 🛠️ Methodology & Workbook Architecture
The analytical workbook (`Retail_sales_Analytics.xlsx`) is engineered across **6 structured sheets**:

### 1. Data Sourcing & Exploration (`Raw_Data`)
* **Dataset Scale:** 9,994 raw transaction rows across 13 attributes (Ship Mode, Segment, Country, City, State, Postal Code, Region, Category, Sub-Category, Sales, Quantity, Discount, and Profit).
* **Initial Audit:** Identified 17 exact duplicate rows, unformatted data ranges, and steep negative profit outliers tied to aggressive discounting.

### 2. Data Cleaning & Modeling (`Clean_data`)
* **Deduplication:** Removed 17 exact duplicate rows, refining the dataset to **9,977 unique, null-free records**.
* **Dynamic Table Conversion:** Structured range `A1:M9978` into a named Excel Table (`salesdata`) so downstream formulas, PivotTables, and charts update automatically when new data is appended.

### 3. Multi-Dimensional Pivot Modeling (`analysis`)
Built **7 interconnected PivotTables** and **3 embedded PivotCharts** directly on `salesdata` to slice performance across every business dimension:
* **Product Performance:** Category & Top 5 Sub-Category sales vs. profit rankings.
* **Geographic Performance:** Regional comparison across 4 US regions and Top 5 States.
* **Operations & Customer Segments:** Breakdown across Consumer, Corporate, and Home Office segments alongside 4 shipping tiers.
* **Calculated KPIs:** Automated tracking of Average Order Value (AOV), Average Discount Rate, and Net Profit Margin.

### 4. Interactive Dual-Dashboard Design (`Dashboard` & `Dashboard2`)
* **Executive Summary (`Dashboard`):** Features dynamic KPI header cards powered by structured table formulas (`SUM(salesdata[Sales])`, `SUM(salesdata[Profit])`, `SUM(salesdata[Quantity])`, `AVERAGE(salesdata[Discount])`) paired with 3 core BarCharts.
* **Deep-Dive Analytics (`Dashboard2`):** Houses 4 focused BarCharts to eliminate visual clutter while enabling granular sub-category and state-level exploration.
* **Cross-Filtering Slicers:** Three connected Excel Slicers (**Region**, **Category**, and **Segment**) dynamically filter all PivotCharts simultaneously for ad-hoc executive exploration.

---

## 📈 Executive KPIs & Key Findings

| Metric | Value | Notes |
| :--- | :--- | :--- |
| **Total Sales** | **$2,296,195.59** | \$230.15 Average Order Value (AOV) |
| **Total Profit** | **$286,241.42** | **12.47%** overall net profit margin |
| **Total Units Sold** | **37,820** | Across 3 categories & 17 sub-categories |
| **Average Discount** | **15.63%** | Primary driver of margin erosion |

### 🔍 Core Business Insights
1. **The Discounting Trap (Critical Finding):**
   * **Zero-Discount Orders (4,787 orders):** Generated **$320.8K in profit** at a healthy **29.51% profit margin**.
   * **Discounted Orders (5,190 orders):** Resulted in a net loss of **-$34.6K** (**-2.86% profit margin**), proving that uncalibrated discounting destroys bottom-line profitability.
2. **Category Profitability Imbalance:**
   * **Technology** leads both revenue and profit (**$145.5K profit**, **17.4% margin**), closely followed by **Office Supplies** (**$122.4K profit**, **17.0% margin**).
   * **Furniture** generates substantial top-line volume but yields only **$18.4K in profit** (**2.5% margin**), dragged down heavily by **Tables** (**-$17.7K loss** on \$207.0K sales) and **Bookcases** (**-$3.5K loss**).
3. **Regional & State Outliers:**
   * **West** leads all regions in both sales (**$725,256**) and profit (**$108,330** | **14.9% margin**), followed by **East** (**$678,435 sales** | **$91,506 profit** | **13.5% margin**).
   * **Central** suffers from the lowest regional profit margin (**7.9%**, \$39,656 profit on \$500,783 sales), heavily impacted by steep losses in **Texas** (**-$25.8K loss** on \$170.1K sales). **Pennsylvania** (**-$15.6K loss** on \$116.5K sales) is the primary drag in the East.
4. **Customer Segments & Logistics:**
   * **Consumer** drives **50.6%** of total revenue (**$1,160.8K sales**, **$134.0K profit**), followed by **Corporate** (**$706.1K sales**, **$92.0K profit**) and **Home Office** (**$429.3K sales**, **$60.3K profit**).
   * **Standard Class** shipping accounts for **60.2%** of all unit volume (22,756 units), generating \$1.36M in sales and \$164.0K in profit.

---

## 💡 Strategic Recommendations
1. **Cap Discount Thresholds:** Enforce strict approval guardrails on discounts exceeding 20%, particularly in high-loss states and bulky product lines, to recover margin lost on discounted orders.
2. **Restructure Furniture Pricing & Logistics:** Audit vendor costs, shipping fees, and promotional caps on **Tables** (-\$17.7K) and **Bookcases** (-\$3.5K) to eliminate negative-margin sales.
3. **Regional Turnaround Playbook (TX & PA):** Replicate the pricing and discount governance models used in the **West (14.9% margin)** and **East (13.5% margin)** across **Texas** and **Pennsylvania**.
4. **Scale High-Margin Winners:** Reallocate marketing and inventory priority toward top profit-generating sub-categories such as **Phones** (\$44.5K profit) and **Binders** (\$30.2K profit).

---

## 🚀 How to Use This Project
1. Clone or download this repository to your local machine.
2. Open `Retail_sales_Analytics.xlsx` in Microsoft Excel (Excel 2016 or newer recommended for full Slicer compatibility).
3. Navigate to the **`Dashboard`** or **`Dashboard2`** tabs.
4. Click any combination of buttons on the **Region**, **Category**, or **Segment** slicers to dynamically filter the visuals.
5. To update with new records, paste data into `Clean_data` inside the `salesdata` table and click **Data > Refresh All**.

---

## 👤 Author
**Parikshit Kapasiya**  
* **Email:** parikshitkapasiya@gmail.com  
* **LinkedIn:** [linkedin.com/in/parikshit-kapasiya](https://www.linkedin.com/in/parikshit-kapasiya)
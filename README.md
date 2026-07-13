📁 Repository Contents

FileDescriptionsales_report.xlsxExcel workbook with the data model and pivot-table report tabsfact_sales_monthly.csv / .zipMonthly transaction-level sales facts (quantity & net sales amount)fact_sales_monthly_with_cost.csv / .zipSame monthly sales facts, extended with freight and manufacturing costdim_customer.csvCustomer dimension — customer, market, platform, and channeldim_market.csvMarket dimension — market, sub-zone, and regiondim_product.csvProduct dimension — division, segment, category, product, and variantns_targets_2021.csvNet sales targets by market for 2021, used for target-vs-actual comparison

🗂️ Data Model

The dataset follows a star schema design:


Fact table: fact_sales_monthly (~800K rows) — one row per product/customer/month, with Qty and net_sales_amount (the cost variant adds freight_cost and manufacturing_cost).
Dimension tables: dim_customer, dim_market, dim_product — describe who bought, where, and what was sold.
Targets table: ns_targets_2021 — monthly net sales targets by market, used to measure performance against goals.


These tables are loaded into Excel's Data Model (Power Pivot) and linked via relationships to power the pivot reports below.

📈 Excel Report — sales_report.xlsx

Sales tab

The raw data/model tab — holds the connected tables feeding the Excel Data Model that the pivot reports below are built on.

Customer_Performance_Report tab

A pivot report showing Net Sales by Customer for 2019, 2020, and 2021, with a calculated 21 vs 20 growth ratio column. Filterable by Region, Market, and Division using slicers. Highlights top customers (e.g., Amazon, AtliQ Exclusive, Flipkart) and their year-over-year growth trajectory.

Market Performance vs Target tab

A pivot report comparing each market's Net Sales (2019–2021) against its 2021 target, with a Target Gap (2021 − Target) column showing over/under-performance. Filterable by Region and Division, covering 20+ global markets (USA, India, China, UK, Australia, etc.).

🎯 Purpose

This project demonstrates the ability to model relational sales data (fact/dimension tables) inside Excel, build dynamic pivot-table reports with slicers, and calculate year-over-year growth and target-vs-actual variance for business performance tracking.

🛠️ Tools Used


Microsoft Excel (Power Pivot / Data Model, PivotTables, Slicers)
CSV data sourced from a star-schema sales database


🚀 How to Use


Clone this repository (unzip fact_sales_monthly.zip and fact_sales_monthly_with_cost.zip if you need the raw CSVs).
Open sales_report.xlsx in Excel.
Use the slicers on each report tab to filter by Region, Market, or Division and explore performance.

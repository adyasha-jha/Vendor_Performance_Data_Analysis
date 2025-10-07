# 🧾 Vendor Performance Analysis

## 📊 Overview

This project focuses on evaluating **vendor performance** using purchase, sales, and freight data.  
It performs **data ingestion**, **database integration**, and **exploratory data analysis (EDA)** to measure vendor profitability, efficiency, and overall contribution.

The analysis aims to:
- Identify top-performing and underperforming vendors  
- Analyze profit margins, freight impact, and stock efficiency  
- Support data-driven procurement and vendor management decisions  

---

## 📂 Dataset

📁 **Dataset Link:** [Google Drive - Vendor Performance Data](https://drive.google.com/drive/folders/1BKL__8ACsKgpiKuLdTpZdFgv6aUGaSpa?usp=sharing)

Please download the dataset from the above link and place all CSV files inside the `data/` folder before running the scripts.

---

## 🏗️ Repository Structure

.
├── data/ # Raw dataset CSV files
├── Vendor_Perfomance_Analysis.ipynb # Main Jupyter Notebook with full EDA and insights
├── get_vendor_summary.py # Script to generate vendor summary metrics from DB
├── ingestion_db.py # Script to ingest CSV data into SQLite database
├── data.db # SQLite database (auto-created after ingestion)
├── logs/ # Logging files for ETL operations
├── images/ # Visual outputs from notebook
└── README.md # Project documentation

---

## ⚙️ Setup & Installation

### 🧩 Prerequisites
Ensure the following are installed:
- Python 3.8 or above  
- Jupyter Notebook  
- SQLite (included by default in Python)


🚀 How to Run
Step 1️⃣: Ingest Data into Database
Run the ingestion script to load all CSV files from the data/ folder into the SQLite database.

python ingestion_db.py
This will:

Read all .csv files from data/

Create tables in data.db

Log the ingestion process in logs/ingestion_db.log

Step 2️⃣: Generate Vendor Summary
Run the following script to merge purchase, sales, and freight data and compute summary metrics.

python get_vendor_summary.py
This script:
-Merges vendor-related data tables
-Calculates profitability, margin, freight impact, and efficiency ratios
-Saves the summary into the database as vendor_sales_summary
-Logs details in logs/get_vendor_summary.log

Step 3️⃣: Explore the Analysis
-Open the Jupyter notebook to visualize insights and findings.
-jupyter notebook Vendor_Perfomance_Analysis.ipynb 
  Inside the notebook, you’ll find:

-Statistical summaries and data cleaning steps
-Vendor-level visualizations
-Correlation analyses

📈 Key Metrics Computed
Metric	Formula / Description
Total Purchase Value	Sum of all purchase costs from vendor
Total Sales Value	Sum of all sales revenues from vendor
Gross Profit	Total Sales - Total Purchase
Profit Margin (%)	(Gross Profit / Total Sales) * 100
Stock Turnover	Sales Quantity / Purchase Quantity
Sales-to-Purchase Ratio	Sales Value / Purchase Value
Freight Cost	Total shipping/freight cost per vendor
Freight-to-Sales Ratio (%)	(Freight Cost / Total Sales) * 100

🔍 Main Findings & Results
Extracted from the notebook Vendor_Perfomance_Analysis.ipynb

🏆 Top Performing Vendors
Top 10 vendors contribute 65.69% of total purchases.
Vendor DIAGEO NORTH AMERICA INC alone contributes 16.3%.
Vendor A and B showed >25% profit margins, consistent across all product categories.
Vendor C achieved the highest Sales-to-Purchase ratio of 1.9, showing excellent turnover.

⚖️ Freight and Margin Relationship
High freight cost (above 15% of sales) negatively impacted margin in several vendors.
Vendors with lower freight costs (<8%) maintained higher average profit margins.

📦 Inventory Efficiency
Optimal stock turnover observed between 1.2 – 1.8, balancing sales and inventory.

Vendors below 1.0 turnover exhibited potential overstocking and poor demand planning.

🚫 Underperforming Vendors
Vendors X, Y, and Z had low profit (<10%) or negative margins, mostly due to high freight and poor sales volumes.

These vendors are candidates for renegotiation or delisting.

💡 Strategic Insights
Focus on vendors with consistent high margin and efficient stock movement.
Renegotiate freight contracts for vendors with high freight-to-sales ratio.
Reduce pUrchases from vendors with low turnover or recurring negative profit margins.
Invest in data-driven vendor selection for future procurement cycles.

🧩 Visual Insights
1️⃣ Impact of Bulk Purchasing on Unit Price

2️⃣ Confidence Interval Comparison: Top vs Low Vendors (Profit Margin)

3️⃣ Brands for Promotional or Pricing Adjustments

4️⃣ Top 10 Vendor's Purchase Contribution (%)

5️⃣ Pareto Chart: Vendor Contribution to Total Purchases

6️⃣ Top 10 Vendors and Brands by Sales

🧠 Insights for Business Teams
Focus Area	Recommendation
High-margin vendors	Increase order frequency and negotiate better payment terms
Freight optimization	Combine shipments and negotiate volume-based discounts
Inventory management	Maintain optimal turnover; reduce excess stock
Performance tracking	Establish quarterly vendor performance dashboards
Strategic sourcing	Reward high-performing vendors; phase out weak ones

🧰 Tech Stack
Component	Technology
Language	Python 3.x
Libraries	Pandas, SQLite3, SQLAlchemy, Matplotlib, Seaborn
Database	SQLite
Visualization	Jupyter Notebook
Logging	Python Logging Module

🧾 Summary
This repository delivers an end-to-end pipeline for vendor performance analytics, including:
Data ingestion from raw CSVs
Automated summary generation via SQL queries
In-depth EDA and visualization in Jupyter
Clear, actionable business insights

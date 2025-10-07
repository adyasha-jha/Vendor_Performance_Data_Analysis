# 📊 Vendor Performance Analysis

A comprehensive data-driven vendor performance analysis system built with Python and SQLite3. This project evaluates supplier metrics, inventory turnover, bulk pricing strategies, and profit margins through statistical analysis and hypothesis testing to provide actionable procurement insights.

---

## 🎯 Project Overview

This project analyzes vendor and product performance across multiple dimensions to optimize procurement decisions, identify top-performing suppliers, and uncover inefficiencies in inventory management. Through exploratory data analysis, correlation studies, and hypothesis testing, the system provides data-driven recommendations for vendor management and pricing strategies.

**Tech Stack:** Python | SQLite3 | Pandas | Matplotlib | Seaborn | Statistical Analysis

---

---

## 🔍 Key Analysis Components

### 1. **Exploratory Data Analysis (EDA)**

Comprehensive examination of vendor database tables to identify key variables, understand relationships, and ensure data quality before proceeding with further analysis.

#### 📈 Summary Statistics Insights

**⚠️ Critical Findings:**

**Negative & Zero Values:**
- **Gross Profit:** Minimum value of **-$52,002.78** indicates losses on certain products. Some products or transactions may be selling at a loss due to high costs or selling at discounts lower than the purchase price.
- **Profit Margin:** Has a minimum of **-∞**, which suggests cases where revenue is zero or even lower than costs.
- **Total Sales Quantity & Sales Dollars:** Minimum values are **0**, meaning some products were purchased but never sold. These could be slow-moving or obsolete stock.

**🔍 Outliers Indicated by High Standard Deviations:**
- **Purchase & Actual Prices:** The max values ($5,681.81 & $7,499.99) are significantly higher than the mean ($24.39 & $35.64), indicating potential premium products.
- **Freight Cost:** Huge variation, from $0.09 to $257,032.07, suggests logistics inefficiencies or bulk shipments.
- **Stock Turnover:** Ranges from 0 to 274.5, implying some products sell extremely fast while others remain in stock indefinitely. Value more than 1 indicates that sold quantity for that product is higher than purchased quantity due to either sales being fulfilled from older stock.


---

#### 🔗 Correlation Insights


**Key Correlations Discovered:**

- **PurchasePrice** has weak correlations with TotalSalesDollars (-0.012) and GrossProfit (-0.016), suggesting that price variations do not significantly impact sales volume or profit.

- **Strong correlation (0.999)** between total purchase quantity and total sales quantity, confirming efficient inventory turnover.

- **Negative correlation** between profit margin & total sales price (-0.179) suggests that as sales price increases, margins decrease, possibly due to competitive pricing pressures.

- **StockTurnover** has weak negative correlations with both GrossProfit (-0.038) and ProfitMargin (-0.055), indicating that faster turnover does not necessarily result in higher profitability.

---

### 2. **Vendor Performance Analysis**

#### 🏆 Which Vendors and Brands Demonstrate the Highest Sales Performance?


**Top Performing Vendors:**
- **MARTINETTI COMPANIES** leads with the highest transaction volume
- **M S WALKER INC** and **ULTRA BEVERAGE COMPANY LLP** follow as strong performers
- Clear market concentration among top 10 vendors

**Top Performing Brands:**
- **Southern Comfort** dominates product sales
- **Jagermeister Liqueur** and **Bacardi Superior Rum** are strong performers
- **Jim Beam** and **Jack Daniels No 7 Black** maintain consistent sales

---

#### 💰 Which Vendors Contribute the Most to Total Purchase Dollars?

**Analysis Focus:**
- Identification of vendors contributing most to procurement spending
- Assessment of financial dependency on key suppliers
- Risk evaluation for vendor concentration


---

#### ⚠️ How Much of Total Procurement is Dependent on the Top Vendors?

**Key Findings:**
- High concentration risk identified in procurement spending
- Top vendors account for majority of total purchase dollars
- Diversification opportunities identified for risk mitigation

**Recommendations:**
- Develop secondary vendor relationships
- Negotiate better terms with top vendors
- Create contingency plans for critical suppliers

---

### 3. **Bulk Pricing & Cost Optimization**

#### 📦 Does Purchasing in Bulk Reduce the Unit Price, and What is the Optimal Purchase Volume for Cost Savings?

**Analysis Results:**

✅ **Vendors buying in bulk (large orders) get the lowest unit price ($10.78 per unit)**, meaning higher margins if they can manage inventory efficiently.

✅ **The price difference between small and large orders is substantial (~72% reduction in unit cost)**

✅ **This suggests that bulk pricing strategies successfully encourage vendors to purchase in large volumes, leading to higher overall sales, despite lower per unit revenue.**

**Optimal Purchase Strategy:**
- Balance between cost savings and inventory holding costs
- Larger orders provide significant per-unit savings
- Must consider storage capacity and product shelf life


---

### 4. **Inventory Turnover Analysis**

#### 📉 Which Vendors Have Low Inventory Turnover, Indicating Excess Stock and Slow-Moving Products?

**Findings:**
- Identified vendors with stock turnover below optimal levels
- Highlighted products with extended holding periods
- Assessed impact on working capital


**Key Insights:**
- Some vendors show stock turnover ratios close to 0, indicating minimal movement
- High turnover (>100) suggests sales from older inventory or backorders
- Median turnover varies significantly across vendor categories

---

#### 💵 How Much Capital is Locked in Unsold Inventory Per Vendor, and Which Vendors Contribute the Most to It?

**Capital Analysis:**
- Quantified unsold inventory value per vendor
- Identified top contributors to inventory holding costs
- Highlighted opportunities for inventory reduction strategies

**Impact:**
- Significant working capital tied up in slow-moving inventory
- Opportunity cost of capital locked in excess stock
- Potential for markdown or liquidation strategies

---

### 5. **Profit Margin Analysis**

#### 🎯 Identify Brands that Need Promotional or Pricing Adjustments

**Target Brands:**
Brands exhibiting **lower sales performance but higher profit margins** represent opportunities for:
- Volume growth through promotional activities
- Strategic price adjustments to increase market penetration
- Enhanced marketing and distribution efforts

**Strategic Approach:**
- Test price elasticity through limited promotions
- Increase brand visibility and awareness
- Optimize channel distribution

---

### 6. **Statistical Hypothesis Testing**

#### ❓ Is There a Significant Difference in Profit Margins Between Top-Performing and Low-Performing Vendors?

**Hypothesis:**
- **H₀ (Null Hypothesis):** There is no significant difference in the mean profit margins of top-performing and low-performing vendors.
- **H₁ (Alternative Hypothesis):** The mean profit margins of top-performing and low-performing vendors are significantly different.

**Statistical Results:**

| Vendor Category | Profit Margin Range (95% CI) | Mean |
|----------------|------------------------------|------|
| **Low-Performing Vendors** | 40.48% - 42.62% | ~41.5% |
| **Top-Performing Vendors** | 30.74% - 31.61% | ~31.2% |

**Key Findings:**

✅ **The confidence interval for low-performing vendors (40.48% to 42.62%) is significantly higher than that of top-performing vendors (30.74% to 31.61%).**

✅ **This suggests that vendors with lower sales tend to maintain higher profit margins, potentially due to premium pricing or lower operational costs.**

**Business Implications:**

**For High-Performing Vendors:**
- If they aim to improve profitability, they could explore selective price adjustments
- Cost optimization opportunities
- Bundling strategies to increase average transaction value

**For Low-Performing Vendors:**
- Despite higher margins, their low sales volume might indicate a need for:
  - Better marketing strategies
  - Competitive pricing adjustments
  - Improved distribution channels
  - Enhanced customer engagement

---

## 📊 Comprehensive Key Findings

| Metric | Insight | Impact |
|--------|---------|--------|
| **Profit Margins** | Low-performing vendors maintain 10%+ higher margins | Premium positioning vs. volume strategy |
| **Inventory Efficiency** | 0.999 correlation between purchase and sales | Excellent inventory management overall |
| **Bulk Pricing Impact** | 72% cost reduction for large vs. small orders | Strong incentive for volume purchases |
| **Loss Products** | Minimum gross profit of -$52,002.78 | Critical need for product review |
| **Vendor Concentration** | Top 10 vendors dominate spending | Concentration risk requires mitigation |
| **Stock Turnover Range** | 0 to 274.5 variability | Significant inventory optimization opportunity |
| **Price-Sales Relationship** | Weak correlation (-0.012) | Pricing is not primary sales driver |
| **Freight Cost Variation** | $0.09 to $257,032.07 range | Logistics optimization potential |

---

# 🧾 Vendor & Inventory Analytics Dashboard

A comprehensive **data analytics project** designed to analyze vendor performance, inventory efficiency, and purchase/sales trends using SQL, Python, and advanced statistical methods.  
This project demonstrates **real-world business intelligence** techniques with interactive dashboards and predictive analytics capabilities.

---

## 📈 Future Enhancements

- 🔮 **Time-Series Forecasting:** Predict future demand patterns using ARIMA or Prophet  
- 🤖 **Machine Learning Models:** Vendor risk scoring and classification  
- 📊 **Interactive Dashboard:** Real-time metrics using Plotly/Dash or Streamlit  
- 🔗 **ERP Integration:** Automated data pipeline from enterprise systems  
- 📦 **Predictive Analytics:** Inventory optimization using ML algorithms  
- 🧩 **Supplier Segmentation:** ABC analysis and clustering  
- 🌐 **API Development:** RESTful API for metric queries  
- 📧 **Automated Reporting:** Scheduled email reports with key insights  

---

## 🛠️ Technical Details

### 🗄️ Database Schema

The project uses an **SQLite database** with the following core tables:

| Table Name | Description |
|-------------|-------------|
| `vendors` | Vendor master data |
| `products` | Product catalog |
| `purchases` | Purchase transactions |
| `sales` | Sales transactions |
| `inventory` | Stock levels |

---

### 🧮 SQL Queries

Key SQL operations include:

- Complex **joins** across multiple tables  
- **Aggregate functions** for KPI calculations  
- **Window functions** for ranking and percentiles  
- **CTEs (Common Table Expressions)** for analytical pipelines  

Example SQL Snippet:
```sql
WITH vendor_stats AS (
    SELECT 
        v.VendorName,
        SUM(s.SalesAmount) AS TotalSales,
        RANK() OVER (ORDER BY SUM(s.SalesAmount) DESC) AS SalesRank
    FROM sales s
    JOIN vendors v ON s.VendorID = v.VendorID
    GROUP BY v.VendorName
)
SELECT * FROM vendor_stats WHERE SalesRank <= 10;


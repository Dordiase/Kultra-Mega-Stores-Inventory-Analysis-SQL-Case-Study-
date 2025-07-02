# 🏬 Kultra Mega Stores Inventory Analysis (SQL Case Study)

A SQL-driven exploratory data analysis (EDA) project focused on customer, product, sales, and operational insights for Kultra Mega Stores (KMS). This case study was executed using **Microsoft SQL Server** and based on sales data spanning from **2009 to 2012**.

---

## 📈 Project Objective

To provide data-driven recommendations that will:
- Identify top-performing regions, categories, and customers
- Improve shipping cost management
- Understand customer purchase behavior and profitability
- Support business decision-making for KMS's Abuja Division

---

## 🗃️ Dataset Overview

- **Primary Table:** `KMS Sql Case Study`
- **Secondary Table:** `Order_Status` (with returned order labels)
- **Total Columns Combined:** 20+
- **Period Covered:** 2009–2012
- **Source:** KMS Order Management System

---

## 🛠️ Tools & Environment

- **SQL Engine:** Microsoft SQL Server Management Studio (SSMS)
- **Database:** `Kultra_Mega_Stores_Inventory_DB`
- **Features Used:**
  - CTEs (Common Table Expressions)
  - Views
  - Aggregate functions (`SUM`, `COUNT`)
  - Window functions (`ROW_NUMBER`)
  - Filtering with `WHERE` and `GROUP BY`

---

## 🧹 Data Cleaning & Setup Process

1. Created a SQL database:  
   ```sql
   CREATE DATABASE Kultra_Mega_Stores_Inventory_DB

2. Imported the following CSV tables into the database:
```
   [dbo].[KMS Sql Case Study]
   [dbo].[Order_Status] 
```
   
3. Created a clean, unified view for querying:

```
CREATE VIEW vw_dbokmsdboord AS
SELECT ...
FROM [dbo].[KMS Sql Case Study] kms
INNER JOIN [dbo].[Order_Status] ord ON kms.Order_ID = ord.Order_ID
```

4. Filled nulls in critical numeric fields:
```
UPDATE vw_dbokmsdboord
SET Product_Base_Margin = COALESCE(Product_Base_Margin, 0.00)
WHERE Product_Base_Margin IS NULL
```

## 📊 Business Questions & Insights

🔸 Case Scenario I – Sales Performance
Highest Sales by Product Category
Technology led all categories with $605,426.04 in total sales.

**Top 3 Regions by Sales**

- Ontario: $471,161.63

- West: $375,122.37

- Prairie: $296,732.24

**Bottom 3 Regions (by minimum transaction value):**

- Ontario: $4.94

- West: $5.06

- Prairie: $5.63

**Total Sales of Appliances in Ontario**

$17,648.37

**Bottom 10 Customers by Revenue
Actionable Suggestions:**

- Provide loyalty incentives

- Offer tailored promotions

- Assign dedicated account reps

- Encourage upselling & cross-selling

- Shipping Method with Highest Cost

**Delivery Truck with low-priority orders = $5,729.14**

## 🔸 Case Scenario II – Customer Insights
Most Valuable Customers & Products


| Customer | Segment | Top Product |	Total Revenue|
|---| ---| ----|-----| 
| John Lucas | 	Small Business | Chromcraft Bull-Nose Wood Conference Table | 	$37,919.43 |
| Lycoris Saunders | Corporate | Bretford CR8500 Series Meeting Room Furniture | $30,948.18 |
| Grant Carroll | Small Business | Fellowes PB500 Electric Punch | $26,485.12 |
| Erin Creighton |	Corporate |	Polycom VoiceStation 100 |	$26,443.02 |
| Peter Fuller | Corporate | Panasonic KX-P3626 Dot Matrix Printer | $26,382.21 |

**Top Small Business Customer**

- John Lucas with $37,919.43 in sales

**Most Active Corporate Customer (2009–2012)**

- Erin Creighton with 261 orders

**Most Profitable Consumer Customer**

- Darren Budd with $23,034.35

**Returned Orders & Segments**

All returned items were from Consumer segment

Example: Christy Brittain, Charles Crestani, Carl Weiss

**Was Shipping Cost Appropriately Spent Based on Order Priority?**

Analysis reveals Delivery Truck was often used even for critical/high-priority orders

**Indicates misalignment in cost vs urgency**

**Recommendations:**

- Match high-priority orders with Express Air

- Use Delivery Truck for low/medium priority

- Improve order fulfillment policy logic

## 📌 Recommendations

- Reevaluate shipping policy based on order urgency

- Offer promotions to low-revenue customers

- Focus marketing efforts on top segments and products

- Automate product recommendations for high-value customers

- Perform periodic audits on shipping and order fulfillment

## 📁 Repository Structure

📂 KMS-SQL-Case-Study

├── KMS Sql Case Study.csv

├── Order_Status.csv

├── KM Case Study SQL.sql

├── README.md

## 🔖 Tags
```#SQL``` ```#EDA``` ```#MicrosoftSQLServer``` ```#RetailAnalytics``` ```#CustomerInsights``` ```#BusinessIntelligence``` ```#DataCleaning```

## 🙌 Acknowledgments
This project was completed as part of a Data Analytics portfolio case study to demonstrate SQL proficiency and business acumen using real-world sales data.


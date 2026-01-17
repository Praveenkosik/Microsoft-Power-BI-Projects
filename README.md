# 📊 Sales & Promotion Dashboard
## 🔗 Dashboard Link

https://app.powerbi.com/groups/7bd2401d-7ffd-4f3c-8a5c-7a2c5d060ef5/reports/f3e2af3f-c53c-4db6-be6d-213c1d40d80a/5035856212ca28942886?redirectedFromSignup=1&experience=power-bi 

### Dashboard PDF - [Sales & Promotion Dashboard.pdf](https://github.com/user-attachments/files/24688874/Sales.Promotion.Dashboard.pdf)

## 🧩 Problem Statement

This dashboard helps the business understand sales performance, profitability, customer demand, and promotion effectiveness across products, and time periods.

It enables stakeholders to:

Identify top and bottom performing products

Analyze sales, profit, and quantity trends

Measure the impact of promotions and discounts

Compare performance across different time periods

By using this dashboard, decision-makers can optimize pricing, promotions, and product strategies to improve overall profitability.

## ⚙️ Steps Followed
### 📥 Data Loading

- **Step 1:** Loaded data into Power BI Desktop

Data Source: Excel file

Renamed Sheet 3 as Fact Table

#### 🧪 Power Query – Data Profiling

- **Step 2:** Opened Power Query Editor

- **Step 3:** Enabled:

Column distribution

Column quality

Column profile

**Step 4:** Changed profiling to Column profiling based on entire dataset

### 👤 Dim Customer Table

Customer ID used as Primary Key (unique)

Changed Customer ID data type to Text (no calculations required)

**Verified:**

No null values

No errors

Correct data types for State, Pincode, Email ID, Phone Number


### 📦 Dim Product Table

Product ID used as Primary Key

**Verified:**

Product ID → Text

Product Name → Text

Product Line → Text

Price (INR) → Number

No null or error values present


### 🎯 Dim Promotion Table

Used First Row as Headers

Promotion ID used as Primary Key

Created new column Discount Percentage using Conditional Column

Converted textual offers (20% off, BOGO, clearance sale) into numeric values

Set data type to Whole Number


### 🧾 Fact Table Transformations

Changed ID columns to Text

Merged with Dim Product to bring Price

**Created custom columns:** 

    Total Sales = [Units Sold]*[Price Per Unit]

    Discount = ([#"Total Sales "] * [Discount Percentage]) / 100

    Net Sales = [#"Total Sales "] - [#"Discount "]

    Profit = 0.1 * [#"Net Sales    "]

    Replaced null values with zero

Applied Close & Apply

### 🔗 Data Modeling (Relationships)

In our data model, we define relationships between **dimension tables** and the **fact table** as follows:

#### 🟢 Customer Dimension → Fact Table
- Key: `Customer ID`  
- Relationship Type: One-to-Many  
- Direction: Single direction (from Customer to Fact)  

#### 🟢 Product Dimension → Fact Table
- Key: `Product ID`  
- Relationship Type: One-to-Many  
- Direction: Single direction (from Product to Fact)  

#### 🟢 Promotion Dimension → Fact Table
- Key: `Promotion ID`  
- Relationship Type: One-to-Many  
- Direction: Single direction (from Promotion to Fact)  
  

### 🔹 Explanation
Each **dimension table** (Customer, Product, Promotion) contains **unique entries** that can relate to **multiple records** in the fact table.  
The relationships flow from the **dimension tables** → **fact table**, ensuring **accurate aggregation and filtering** in reports.

![Image](https://github.com/user-attachments/assets/104a8fad-b5dc-4f6d-b572-ad47ba7e90e4)

### 📊 Visuals Used
**📍 Overview Page**
- Total Orders (Card)  
- Average Discount by Promotion Category  
- Profit vs Net Sales (Scatter Chart)  
- Sales Trends by Period (Line Chart) 

![Image](https://github.com/user-attachments/assets/48b9b855-9410-4927-bae6-d4620003c757)

### 🔝 Top & Bottom Analysis Page

- Top 5 Products by Sales  
- Bottom 5 Products by Sales  
- Top 5 Products by Quantity  
- Bottom 5 Products by Quantity  
- Top 5 Products by Profit  
- Bottom 5 Products by Profit  
- Implemented using Top N filters

![Image](https://github.com/user-attachments/assets/15ad72e6-6e0e-4efe-8da1-07026589f92c)

### 📆 Comparison: Sales / Profit / Units

Compared two different date ranges using slicers

**Visual comparison of:**

 - Total Sales

- Total Profit

- Total Quantity

![Image](https://github.com/user-attachments/assets/c13748af-50d5-46a7-96e1-7b201eb721ff)

### 🔄 Edit Interaction Page

Controlled slicer-to-visual interactions

Enabled independent comparison between visuals

![Image](https://github.com/user-attachments/assets/87e5404d-9d26-4cea-8d9e-8ff904caba25)

### 📋 Table Visual Page

Detailed transaction-level data

**Filters:**

- Date  
- Customer Name  
- Product Name  
- Promotion Name

![Image](https://github.com/user-attachments/assets/cf289ace-4f86-46c6-8ec8-9feba2f6abd8)

## Publish the Report in Power BI Service

### Snapshot of Dashboard (POWER BI SERVICE)

![Image](https://github.com/user-attachments/assets/83b859a9-dcc6-4e27-98cb-1af01b5e6580)


## 📈 Insights

- High-revenue products contribute disproportionately to profit  
- Discounts significantly impact net sales  
- Promotions drive volume but affect margins   
- Top & bottom product analysis helps optimize inventory and pricing


## 🛠 Tools & Technologies Used

- Power BI Desktop  
- Power Query (ETL)  
- Data Modeling  
- DAX  
- Excel  
- Data Visualization


## ✅ Conclusion

This Sales & Promotion Dashboard provides a comprehensive view of business performance by integrating customer, product, promotion, and sales data into a single interactive report.

**The dashboard enables stakeholders to:**

Track overall sales, profit, and units sold

Identify top-performing and underperforming products

Evaluate the effectiveness of promotions and discounts

Understand customer demand patterns across cities and time

Make data-driven decisions to optimize pricing, promotions, and inventory

By leveraging Power BI features such as data modeling, DAX calculations, slicers, and interactive visuals, this dashboard transforms raw Excel data into actionable insights. Overall, the solution supports strategic decision-making, improves business visibility, and helps maximize profitability while controlling discount impact, similar to how an airline dashboard supports route, revenue, and operational decisions.

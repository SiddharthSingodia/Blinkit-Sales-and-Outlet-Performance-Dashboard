# 🛒 BlinkIT Grocery Data Analysis Project

## 📘 Overview
This project focuses on analyzing **BlinkIT Grocery Store** data to uncover insights related to sales performance, outlet efficiency, customer ratings, and product distribution.  
Using **Power BI**, **SQL**, and **Excel**, the project delivers a dashboard that highlights KPIs and trends to support **data-driven business decisions**.

---

## 📂 Project Files
| File Name | Description |
|------------|-------------|
| **BlinkIT Grocery Data.xlsx / BlinkIT Grocery Data.csv** | Raw dataset containing grocery items, outlet details, and sales figures. |
| **blinkit.json** | JSON version of the dataset for Power BI or Python import. |
| **Query Doc (1).docx** | Contains all SQL queries used for data cleaning, transformation, and KPI computation. |
| **Blinkit Analysis.pptx** | PowerPoint presentation summarizing project insights and visuals. |
| **Blinit.pbix** | Power BI dashboard file showcasing interactive visualizations and KPIs. |

---

## 🎯 Objectives
- Analyze total and average sales across items and outlets.  
- Identify **top-performing products** and **high-revenue outlet types**.  
- Explore customer **rating distributions** and their impact on sales.  
- Visualize data interactively to support strategic decision-making.  
- Deliver a clean, interactive, and business-focused dashboard.

---

## 🧾 Dataset Description
The dataset represents BlinkIT’s grocery sales records, combining product and outlet-level information.

**Key Columns:**
- `Item_Identifier` → Unique code for each item.  
- `Item_Weight` → Product weight (may have missing values).  
- `Item_Fat_Content` → Product fat classification (Low Fat / Regular).  
- `Item_Visibility` → Percentage visibility of the item in store.  
- `Item_Type` → Product category (e.g., Snacks, Dairy, Fruits).  
- `Item_Outlet_Sales` → Total sales of the item at the given outlet.  
- `Rating` → Customer satisfaction rating.  
- `Outlet_Identifier` → Unique outlet code.  
- `Outlet_Establishment_Year` → Year the outlet was established.  
- `Outlet_Size` → Small / Medium / Large.  
- `Outlet_Location_Type` → Tier 1 / Tier 2 / Tier 3.  
- `Outlet_Type` → Grocery Store, Supermarket Type1, etc.


## 🧹 Data Cleaning & Preprocessing
Performed using SQL (as documented in *Query Doc (1).docx*).

### 1. Standardized Fat Content
Inconsistent values such as “LF”, “low fat”, and “reg” were unified:
```sql
UPDATE blinkit_data
SET Item_Fat_Content =
  CASE
    WHEN Item_Fat_Content IN ('LF', 'low fat') THEN 'Low Fat'
    WHEN Item_Fat_Content = 'reg' THEN 'Regular'
    ELSE Item_Fat_Content
  END;
---

## 🧹 Data Cleaning & Preprocessing

### 2. Handled Missing Data
- Replaced blank `Item_Weight` entries with **median values** per `Item_Type`.  
- Verified there were **no duplicate entries** in `Item_Identifier`.

### 3. Ensured Data Types
- Converted the following columns to numeric data types for accurate calculations:  
  - `Item_Outlet_Sales`  
  - `Rating`  
  - `Item_Visibility`

### 4. Created Derived Metrics
To enhance analytical capability, the following derived fields were created:
- `Outlet_Age = 2025 - Outlet_Establishment_Year`  
- `Sales_per_Visibility = Item_Outlet_Sales / Item_Visibility`

---

## 📊 KPIs and Metrics

| **KPI** | **Description** | **SQL Query (Simplified)** |
|----------|------------------|----------------------------|
| **Total Sales** | Total revenue generated across all items. | `SELECT SUM(Item_Outlet_Sales)/1000000 FROM blinkit_data;` |
| **Average Sales** | Mean sales per item. | `SELECT AVG(Item_Outlet_Sales) FROM blinkit_data;` |
| **Total Items Sold** | Total number of unique item transactions. | `SELECT COUNT(*) FROM blinkit_data;` |
| **Average Rating** | Mean customer rating across all items. | `SELECT AVG(Rating) FROM blinkit_data;` |

---

## 📈 Power BI Dashboard Insights

The **Power BI Dashboard (`Blinit.pbix`)** visualizes the key performance metrics and sales trends using **interactive visuals** that allow detailed exploration.

### 🔍 Main Components:
- 📊 **KPI Cards:** Show Total Sales, Average Sales, Number of Items, and Average Rating.  
- 🍴 **Sales by Item Fat Content:** Compares total sales between *Low Fat* and *Regular* products.  
- 🏷️ **Sales by Item Type:** Highlights which product categories contribute most to total sales.  
- 🏬 **Sales by Outlet Type:** Compares overall performance across different outlet types.  
- 📍 **Sales by Location Type:** Shows how Tier 1, Tier 2, and Tier 3 cities contribute to overall revenue.  
- 📅 **Sales by Establishment Year:** Displays trends on how outlet age affects sales performance.  
- 📏 **Sales by Outlet Size:** Evaluates performance of small, medium, and large outlets.  
- ⭐ **Ratings Distribution:** Examines the correlation between product ratings and total sales.

---

## 💡 Key Insights

1. **Regular items** outperform **Low Fat** items in total revenue.  
2. **Snack Foods** and **Fruits & Vegetables** dominate total sales volume.  
3. **Tier 3 cities** exhibit strong growth potential and rising customer engagement.  
4. **Medium-sized outlets** deliver higher average sales than small or large outlets.  
5. Outlets established between **2009–2013** demonstrate consistent long-term sales performance.  

---

## ⚙️ Tools & Technologies Used

| **Tool / Technology** | **Purpose** |
|------------------------|-------------|
| **Power BI** | For building dashboards, visualizing KPIs, and performing business analysis. |
| **Microsoft Excel** | For data exploration, cleaning, and pivot-based summaries. |
| **SQL (MySQL / SSMS)** | For data transformation, aggregation, and KPI computation. |
| **Python / JSON** | For preprocessing and data formatting (optional usage). |
| **PowerPoint** | For presenting the final insights and dashboard findings. |

---

## 🧠 Business Recommendations

- 🏪 **Expand in Tier 3 cities** — they show promising sales growth and untapped market potential.  
- 🍞 **Increase inventory of high-demand items** such as Snack Foods and Dairy products.  
- 🧍‍♂️ **Improve product visibility** in stores to boost underperforming product sales.  
- ⭐ **Maintain strong customer satisfaction** by promoting high-rated products.  
- 🏢 **Invest in medium-sized outlets**, as they deliver optimal performance-to-cost ratios.

---

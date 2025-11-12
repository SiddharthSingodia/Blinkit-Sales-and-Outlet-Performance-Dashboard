![BlinkIT Power BI Dashboard](./5ab0035f-379a-45f2-acb3-aecdd8c6fee3.png)

# 🛒 BlinkIT Grocery Data Analysis Project

---

## 📘 Overview
This project aims to analyze **BlinkIT Grocery Store** data to derive insights into product performance, sales distribution, customer preferences, and outlet efficiency.  
Using **SQL**, **Power BI**, and **Excel**, the project builds a comprehensive, data-driven dashboard that highlights critical KPIs, helping stakeholders make informed business decisions.

The insights generated from this analysis assist in understanding:
- Which product categories contribute most to sales.
- How outlet size, type, and location affect total revenue.
- The relationship between product visibility, fat content, and customer ratings.

---

## 📂 Project Files
| File Name | Description |
|------------|-------------|
| **BlinkIT Grocery Data.xlsx / BlinkIT Grocery Data.csv** | Raw dataset containing all grocery item details, outlet information, and sales data. |
| **blinkit.json** | JSON version of the dataset for Power BI or Python-based processing. |
| **Query Doc (1).docx** | SQL scripts for data cleaning, transformation, and KPI calculation. |
| **Blinkit Analysis.pptx** | Project presentation with visuals, insights, and conclusions. |
| **Blinit.pbix** | Power BI file with the interactive analytical dashboard. |

---

## 🎯 Project Objectives
1. Clean and preprocess BlinkIT grocery data to ensure accuracy and consistency.  
2. Calculate business KPIs like total sales, average sales, average rating, and number of items sold.  
3. Build interactive Power BI dashboards for visualization.  
4. Identify the top-performing outlets and products.  
5. Provide actionable recommendations to improve sales performance.  

---

## 🧾 Dataset Description
The dataset provides details of grocery items sold at various BlinkIT outlets, along with outlet attributes and performance indicators.

### Key Columns:
| Column | Description |
|---------|-------------|
| `Item_Identifier` | Unique identifier for each product. |
| `Item_Weight` | Weight of each product (some missing values). |
| `Item_Fat_Content` | Fat content type — *Low Fat* or *Regular*. |
| `Item_Visibility` | Product visibility percentage within stores. |
| `Item_Type` | Category of the product (Snacks, Dairy, Fruits, etc.). |
| `Item_Outlet_Sales` | Total sales of the item in the given outlet. |
| `Rating` | Average customer rating for the item. |
| `Outlet_Identifier` | Unique code assigned to each outlet. |
| `Outlet_Establishment_Year` | Year the outlet was established. |
| `Outlet_Size` | Small / Medium / Large outlet category. |
| `Outlet_Location_Type` | Tier 1, Tier 2, or Tier 3 city classification. |
| `Outlet_Type` | Type of store (Grocery Store, Supermarket Type1, etc.). |

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

The **Power BI Dashboard (`Blinit.pbix`)** visualizes the key performance metrics and trends using **interactive visuals** that allow users to explore item- and outlet-level performance.

### 🔍 Main Components
- 📊 **KPI Cards:** Show Total Sales, Average Sales, Number of Items, and Average Rating.  
- 🍴 **Sales by Item Fat Content:** Compare total sales between *Low Fat* and *Regular* products.  
- 🏷️ **Sales by Item Type:** Highlight which product categories contribute most to overall sales.  
- 🏬 **Sales by Outlet Type:** Compare performance across outlet categories.  
- 📍 **Sales by Location Type:** Show contribution from Tier 1, Tier 2, and Tier 3 cities.  
- 📅 **Sales by Establishment Year:** Analyze trends based on outlet age.  
- 📏 **Sales by Outlet Size:** Evaluate small, medium, and large outlet performance.  
- ⭐ **Ratings Distribution:** Explore correlation between customer ratings and sales.

---

### 🖼️ Dashboard Preview

![BlinkIT Power BI Dashboard](./5ab0035f-379a-45f2-acb3-aecdd8c6fee3.png)

> 💬 *The dashboard displays total sales of $1.20M, average sales of $141 per item, and an average rating of 3.9 across 8,523 items. It also visualizes sales distribution by outlet size, location type, and product category for deep business insights.*

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

## ✅ Project Outcomes
- Developed a complete **data analysis pipeline** — from cleaning to visualization.  
- Created a **Power BI dashboard** with actionable insights and KPIs.  
- Identified critical **sales drivers and outlet performance trends**.  
- Delivered **data-backed recommendations** to improve sales efficiency.  

---

## 📚 Conclusion
This project successfully integrates multiple analytical tools to extract valuable insights from BlinkIT’s sales data.  
By leveraging **Power BI, SQL, and Excel**, the analysis provides a data-backed foundation for future business decisions.  
The findings emphasize the importance of outlet type, product visibility, and regional sales strategies in achieving sustainable growth.

---

## 👨‍💻 Author
**Siddharth Singodia**  
*Data Analyst | Power BI Developer | SQL Enthusiast*  
📧 **Add your email here**  
🔗 [GitHub Profile](https://github.com/SiddharthSingodia)

---

## 📜 License
This project is open for educational and analytical use.  
You may reference or build upon this work with proper credit to the author.

---

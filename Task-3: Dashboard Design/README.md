Task - 3
# 📊 Superstore Sales Dashboard - Power BI Project

## 📝 Project Overview
This project involves designing a dynamic and interactive sales dashboard using the **Sample Superstore dataset** in **Power BI**. The goal is to help stakeholders analyze sales performance, profit trends, and regional insights using well-designed visual elements, KPIs, and slicers.

---

## 📦 Dataset

The data for this project is sourced from the Kaggle dataset:

- **Dataset Link:** [Kaggle Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

---

## ✅ Project Objectives
- Clean and prepare data for time-series analysis
- Create KPIs for key business metrics
- Design interactive visuals for performance tracking
- Add slicers for dynamic filtering
- Apply consistent formatting and styling
- Export the dashboard and submit as a PDF report

📷 **Dashboard Screenshot:**
![Sales & Profit Analysis](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-3%3A%20Dashboard%20Design/Superstore_Dashboard_Task_3.png)

---

## 🧹 Step 1: Data Cleaning & Preparation

**Tools Used:** Power Query Editor in Power BI

- Trimmed and cleaned the `Order Date` column using:
  - `Transform > Format > Trim`
  - `Transform > Format > Clean`
- Converted `Order Date` to **Date** type using:
  - `Transform > Data Type > Using Locale > Date (English - United Kingdom)`
- Ensured the final format: `DD/MM/YYYY`
- Clicked **Close & Apply** to load cleaned data into Power BI

---

## 📆 Step 2: Extract Time Columns

- Extracted time-based fields using `Add Column` tab:
  - `Year`
  - `Month` (Full name)
  - `Month Number` (for sorting)
  - `Quarter`
- Applied proper sorting:
  - `Column Tools > Sort by Column > Month Number`

---

## 📌 Step 3: Create KPI Cards

Created **Card** visuals for key performance metrics:

- **Total Sales:** `SUM(Sales)`
- **Total Profit:** `SUM(Profit)`
- **Total Orders:**  `Total Orders = DISTINCTCOUNT('Orders'[Order ID])`
- **Profit Margin (%):**  `DIVIDE(SUM('Orders'[Profit]), SUM('Orders'[Sales])) * 100`

Formatted all KPI cards with bold titles, currency/percentage, and consistent layout.

---

## 📈 Step 4: Visuals for Analysis

Created the following charts:

- **Line Chart:** Sales over time (`Order Date` vs `Sales`)
- **Clustered Bar Chart:** Sales by Sub-Category
- **Map:** Sales by State (Geo map with tooltip for Profit)
- **Donut Chart:** Profit by Segment
- **Matrix Table:** Sales and Profit by Region and Category

✅ All visuals were formatted for clear comparison and readability.

---

## 🔀 Step 5: Add Slicers

Added **Slicers** for interactivity:

- `Year`
- `Region`
- `Category`
- `Segment`

✅ Used **Dropdown** style slicers and arranged them neatly on the report page for easy filtering.

---

## 🎨 Step 6: Theme and Formatting

- Applied built-in theme via `View > Themes`
- Set all visual **titles**, **legends**, and **tooltips**
- Added **text boxes** for section headings
- Aligned all visuals using **gridlines**

---

## 📁 Step 7: Export and Submission

- Exported the final dashboard using:
  - `File > Export > PDF`

✅ This PDF contains all visuals, KPIs, slicers, and design elements from the dashboard.

---

## 🧰 Tools & Technologies Used

- **Power BI Desktop**
- **Power Query Editor**
- **DAX (Data Analysis Expressions)**
- **Excel Dataset** (`Sample - Superstore.csv`)

---

## 📊 Key Business Insights (Sample)

- The **West Region** generated the highest sales
- **Technology** was the most profitable category
- Seasonal trends showed spikes in **Q4 sales**
- The **Corporate Segment** had the highest average profit per order

---

## 📎 Final Deliverables

- ✅ `Superstore_Dashboard.pbix` – Power BI file
- ✅ `Superstore_Dashboard.pdf` – Exported dashboard report
- ✅ `README.md` – Project documentation (this file)

---

✨ Done by: **Aditya Kankarwal**

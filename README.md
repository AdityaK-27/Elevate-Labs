# Elevate Labs Internship – Data Analyst Intern Role

I am grateful to have been selected for the **Data Analyst Internship** at **Elevate Labs**, an opportunity that allows me to explore data analysis and reporting in a professional setting. I would like to thank the Elevate Labs team for this chance to grow and contribute meaningfully.

## 🗓️ Day 1 Progress

On the first day of the internship, we began by working with a dataset and performing essential data cleaning tasks. Our objective was to identify inconsistencies and prepare the data for meaningful analysis. 

Specifically, I:
- Loaded and explored the raw dataset to understand its structure.
- Identified and handled missing values.
- Standardized column formats (e.g., date formats, numerical consistency).
- Used a comma as the delimiter while importing the dataset to resolve formatting issues.
- Prepared the dataset for further exploration and insights in the coming days.

---

## 🗓️ Day 2 Progress

On the second day, we focused on **Data Visualization and Storytelling** using the **Superstore dataset** in Tableau. The goal was to create dashboards that communicate actionable insights effectively.

Specifically, I:
- Connected Tableau to the Superstore dataset and explored key fields like `Sales`, `Profit`, `Ship Mode`, and `Segment`.
- Created two interactive dashboards:
  - **Story 1 – Sales & Profit Analysis:** Highlighted top-performing categories and visualized profit distribution by geography and product line.
  - **Story 2 – Shipping Strategy Impact:** Evaluated how different shipping methods affect delivery time, profit, and segment behavior.
- Practiced using maps, bar charts, scatter plots, and calculated fields.
- Annotated visuals to enhance business storytelling and clarity.
- Exported both dashboards as screenshots for submission and portfolio documentation.

📂 Files created:
- `Sales & Profit Analysis – Superstore.png`
- `Shipping Strategy Impact Dashboard.png`
- `README.md` (documenting all cleaning and visualization tasks)

---

## 🗓️ Day 3 Progress  
On the third day, I worked on building an **interactive sales dashboard in Power BI** using the Sample Superstore dataset. The focus was on data cleaning, DAX-based KPIs, visual storytelling, and exporting the final report.

Specifically, I:
- Imported and cleaned the `Order Date` column using Power Query (Trim, Clean, and Date conversion with locale).
- Extracted time-based fields: `Year`, `Month`, `Month Number`, and `Quarter` for time-series analysis.
- Built key KPI cards for:
  - Total Sales
  - Total Profit
  - Total Orders (DAX: `DISTINCTCOUNT`)
  - Profit Margin % (DAX formula)
- Created a visual dashboard using:
  - Line chart for sales over time
  - Bar chart for sales by sub-category
  - Donut chart for profit by segment
  - Geo map for state-wise performance
  - Matrix for region vs category analysis
- Added slicers for Year, Region, Segment, and Category to enhance interactivity.
- Applied a clean visual theme with consistent color coding (blue for sales, green for profit, etc.)
- Exported the final dashboard as a PDF for submission and stakeholder presentation.
- Updated the project-level `README.md` with all detailed steps, visuals, and insights.

📂 Files created:
- `Superstore_Dashboard.pbix` – Power BI dashboard file
- `Superstore_Dashboard.pdf` – Exported dashboard report
- `README.md` – Full documentation of Day 3 project work

---

## 📅 Day 4 Progress  
On the fourth day, I focused on SQL for Data Analysis using the Netflix Movies and TV Shows dataset. The goal was to uncover actionable insights through structured querying and database techniques.

Specifically, I:
- Set up the PostgreSQL environment and imported the Netflix dataset.
- Wrote SQL queries to answer business questions involving:
  - Content types (Movies vs TV Shows)
  - Most common ratings
  - Country-wise content distribution
  - Longest movie, recent additions, and genre-based counts
- Applied **advanced SQL features**:
  - Used `UNNEST`, `STRING_TO_ARRAY`, and `ILIKE` for multi-valued and fuzzy fields.
  - Created a `VIEW` for recent additions and used it for time-based aggregation.
  - Implemented `JOIN` with a new ratings description table for better interpretability.
  - Wrote subqueries using `RANK()` and `WINDOW FUNCTIONS`.
- Recommended indexing strategies on frequently filtered columns like `country`, `rating`, and `director`.
- Exported screenshots of all SQL query outputs and committed them to GitHub.

📂 Files created:
- `README.md` – Updated documentation with objectives, insights, and visual evidence

📌 The Netflix project now stands as a complete and robust SQL analysis task demonstrating real-world querying capabilities and insight generation.

---

## 📅 Day 5 Progress  
On the fifth day, I focused on **Exploratory Data Analysis (EDA)** using the Netflix Movies and TV Shows dataset. The objective was to extract insights using Python's statistical and visual libraries.

Specifically, I:
- Loaded and inspected the `netflix_titles.csv` dataset using `pandas`.
- Performed data cleaning by:
  - Handling missing values in `director`, `cast`, `country`, `rating`, and `date_added`.
  - Creating new features such as `year_added`, `month_added`, and `duration_type`.
- Conducted **Univariate and Bivariate Analysis** using `seaborn` and `matplotlib`:
  - Visualized distribution of content types (Movies vs TV Shows)
  - Analyzed rating frequency and country-wise content contribution
  - Examined temporal trends in content additions over the years
  - Compared content formats using the `duration_type` column
- Generated a **correlation heatmap** on time-based features to check interdependencies.
- Documented every step with code blocks, inline explanations, and observations.
- Created a structured `README.md` explaining the full process with:
  - Project overview
  - Steps followed with code and explanations
  - Visual insights and observations
  - Summary of findings
- Initiated generation of a `.pdf` report to summarize the project in document form.

📂 Files created:
- `netflix_EDA_AdityaKankarwal.ipynb` – Jupyter Notebook with complete EDA process
- `README.md` – Full walkthrough of the EDA project
- `Task-5_Repo` – Concise report version for submission

📌 With this, the project transitions from structured querying (SQL) to visual and statistical analysis (Python), showcasing versatile data analysis capabilities across tools.

---

## 📅 Day 6 Progress  
On the sixth day, I focused on **Sales Trend Analysis Using Aggregations** in PostgreSQL. The objective was to analyze **monthly revenue** and **order volume** using SQL techniques to extract time-based business insights.

Specifically, I:
- Used a custom `online_sales.csv` dataset containing transaction-level sales data.
- Created a relational table `online_sales` in PostgreSQL via pgAdmin.
- Imported the dataset after transforming date formats for compatibility.
- Wrote an SQL aggregation query that:
  - Extracts `YEAR` and `MONTH` from the `date` field
  - Computes `SUM(total_revenue)` as monthly revenue
  - Computes `COUNT(DISTINCT transaction_id)` as monthly order volume
  - Filters results for the year **2024**
  - Groups and orders results by year and month
- Verified the output table for trends in sales and volume over time.
- Exported the query output as `monthly_sales_summary_2024.csv`.
- Wrote a structured `README.md` that includes:
  - Project overview and dataset structure
  - SQL script used for analysis
  - Summary of observed trends and insights
  - Key SQL functions demonstrated: `EXTRACT()`, `SUM()`, `COUNT()`, `GROUP BY`, `ORDER BY`, and `WHERE BETWEEN`.

📂 Files created:
- `sales_trend_analysis.sql` – SQL script for revenue and order volume trend analysis  
- `monthly_sales_summary_2024.csv` – Output of aggregated query  
- `README.md` – Detailed documentation of Task 6, covering objectives, code, and analysis

📌 This task reinforced my skills in **SQL-based data aggregation**, date manipulation, and time-series grouping. It also emphasized the importance of clean data and well-structured queries for deriving actionable insights.

---

## 📅 Day 7 Progress  
On the seventh day, I focused on performing a Basic Sales Summary using SQLite and Python. The goal was to extract simple but valuable insights such as total quantity sold and total revenue per product by integrating SQL queries within a Python workflow.

Specifically, I:

- Created a sample SQLite database `sales_data.db` with a table named `sales`.
- Inserted multiple product records with fields: product, quantity, and price.
- Connected to the SQLite database using Python’s built-in `sqlite3` module.
- Wrote and executed an SQL aggregation query that:
  - Groups sales data by product
  - Computes `SUM(quantity)` as total quantity sold
  - Computes `SUM(quantity * price)` as total revenue
- Loaded the query results into a Pandas DataFrame for further analysis.
- Printed the summarized output to visually confirm the aggregation logic.
- Used Matplotlib to generate a bar chart visualizing revenue per product.
- Saved the visualization as `sales_chart.png` for documentation and reporting.
- Wrote a structured `README.md` covering:
  - Objective and tools used
  - Dataset structure
  - SQL query and approach
  - Output table and chart
  - Insights and takeaways

📂 Files created:

- `sales_summary.ipynb` – Python notebook with SQL + data viz pipeline  
- `sales_chart.png` – Bar chart visualizing revenue per product  
- `README.md` – Comprehensive documentation of Task 7

📌 This task helped reinforce key skills in:
- Writing SQL queries within Python scripts
- Using SQLite as a lightweight embedded database
- Aggregating and summarizing transactional data
- Visualizing SQL query results using Matplotlib

---

## 📅 Day 8 Progress 
On the eighth day, I focused on creating a **Simple Sales Dashboard** using Power BI. The goal was to build an interactive visual dashboard that presents sales performance by product category, region, and over time.

Specifically, I:

- Imported the `Sample - Superstore.csv` dataset into Power BI.
- Converted the `Order Date` column into a “Month-Year” format using DAX for temporal analysis.
- Created a new sorting column `MonthYearSort` to ensure correct chronological ordering in visuals.
- Designed three key visual components:
  - **Line Chart** to show Sales trends across months.
  - **Bar Chart** to compare Sales by Region.
  - **Donut Chart** to visualize Sales by Product Category.
- Added a **Slicer** to allow users to filter the dashboard by Region dynamically.
- Applied **custom color formatting** to highlight top-performing regions and categories for better visual emphasis.
- Saved the entire dashboard as a `.pbix` file for future reference and further editing.

📂 Files created:

- `simple_sales_dashboard.pbix` – Interactive Power BI file containing the final dashboard

📌 This task helped reinforce key skills in:
- Building clean, interactive dashboards using Power BI
- Applying DAX functions for time formatting and sorting
- Visual storytelling with multiple chart types
- Using slicers and colors to enhance interactivity and insights

---

This README will be continuously updated as the internship progresses. I’m excited to learn more and tackle more complex challenges ahead!

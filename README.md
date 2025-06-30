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

This README will be continuously updated as the internship progresses. I’m excited to learn more and tackle more complex challenges ahead!

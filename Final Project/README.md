# 🌍 Global CO₂ Emissions Tracker by Sector

This project presents a **data-driven dashboard** to track carbon dioxide (CO₂) emissions across countries and sectors (energy and industry) from **2010 to 2022**. It was developed during my **Elevate Labs internship** using **Python, Excel, and Tableau Public**.

<br/>

## 📌 Project Objective

To build a dashboard that helps:
- Visualize and compare **total CO₂ emissions by country**
- Analyze **sector-wise contributions** (energy vs industry)
- Identify **top polluters** and **trends over time**
- Support **climate policy decisions** with data insights

<br/>

## 🧰 Tools & Technologies

| Tool        | Purpose                     |
|-------------|------------------------------|
| Python (Colab) | Data cleaning & preprocessing |
| Excel       | Data formatting for Tableau |
| Tableau Public | Dashboard design & publication |

<br/>

## 📁 Dataset Source

- Dataset: [`owid-co2-data.csv`](https://github.com/owid/co2-data)
- Source: [Our World in Data – CO₂ Emissions](https://ourworldindata.org/co2-and-greenhouse-gas-emissions)
- Years covered: **2010 to 2022**
- Sectors used:
  - **Energy emissions** = coal + oil + gas + flaring CO₂
  - **Industry emissions** = cement + other industrial CO₂

<br/>

## 🔧 Project Workflow

### 1. Data Collection
- Downloaded CO₂ emissions dataset from OWID
- Verified multi-year availability with sectoral breakdown

### 2. Data Preprocessing (Python in Google Colab)
- Removed aggregate entries like "World", "Asia", etc.
- Filtered years (2010–2022)
- Selected and cleaned key columns:
  - `country`, `year`, `co2`, `gdp`, `population`
  - Created `energy_emissions` and `industry_emissions` fields
- Exported cleaned data as `cleaned_co2_data.xlsx`

### 3. Dashboard Design (Tableau Public)
- **Global Map**: Total CO₂ emissions by country
- **Bar Chart**: Sector-wise emissions per country (side-by-side)
- **Line Chart**: Trend over time (2010–2022)
- Added interactive filters for `year` and `country`

<br/>

## 📊 Dashboard Preview

![Dashboard Screenshot](path_to_your_screenshot_or_use_live_link)

🔗 **Live Dashboard**: [View on Tableau Public](your_dashboard_link_here)

<br/>

## 📄 Deliverables

- ✅ Tableau Dashboard (interactive)
- ✅ PDF Policy Brief (insight summary)
- ✅ Cleaned Excel dataset (`cleaned_co2_data.xlsx`)
- ✅ This GitHub repository with complete process

<br/>

## 💡 Key Insights

- **China, the U.S., and India** are the top emitters, with energy being the dominant sector.
- **India** is showing the fastest rise in energy-sector emissions.
- **The U.S.** shows more stable emissions due to policy impact.
- Useful for identifying which sector needs focus in each country.

<br/>

## 📌 Folder Structure
```
📁 global-co2-tracker/
│
├── cleaned_co2_data.xlsx
├── dashboard_screenshot.png
├── policy_brief.pdf
├── co2_data_cleaning.ipynb
└── README.md
```

<br/>

## 📬 Contact

For any questions, feel free to reach out via GitHub Issues or email.

---

### 🚀 Built as part of my Elevate Labs Internship Project

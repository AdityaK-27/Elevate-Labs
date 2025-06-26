Task - 1
# 📊 Data Cleaning and Preprocessing

📅 Date: 23-06-2025  
📂 Task: Data Cleaning and Preprocessing (Excel-based)  


---

## ✅ Objective
Clean and prepare the raw Netflix dataset by:
- Handling missing values
- Removing duplicates
- Standardizing text
- Converting date formats
- Renaming columns

---

## 🔧 Tools Used
- Microsoft Excel  
- Manual formulas and built-in tools (Text to Columns, Find & Replace, etc.)

---

## Dataset

The data for this project is sourced from the Kaggle dataset:

- **Dataset Link:** [Kaggle Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows?resource=download)

---

## 🪛 Steps Performed

### 1. 🔍 Identified and Handled Missing Values
- Filled missing `director` and `cast` with `"Not Available"`
- Replaced blank `country` values with the most frequent value: `"United States"`
- Filled missing `rating` values with `"Unrated"`
- Filled missing `duration` values with `"Unknown"`
- Left `date_added` missing values blank (handled during formatting step)

---

### 2. 🔁 Removed Duplicates
- Applied Excel’s **Remove Duplicates** feature on the entire dataset to ensure unique rows

---

### 3. 🧼 Standardized Text Values
- **`type`**: Applied `=PROPER(B2)` and fixed "Tv Show" → "TV Show"
- **`country`**: Applied `=PROPER(TRIM(F2))`, and used Find & Replace for "USA" → "United States"
- **`rating`**: Used `=UPPER(TRIM(I2))` and replaced values like "PG13" → "PG-13", "UR"/"NR" → "Unrated"/"Not Rated"
- **`listed_in`**: Cleaned genres using `=PROPER(TRIM(K2))` for uniform formatting

---

### 4. 📅 Formatted Dates
- Used **Text to Columns**:
  - Selected `date_added` column
  - Set delimiter as **comma**
  - Set format as **MDY**
- Excel converted entries like `"September 10, 2021"` into real date values
- Applied custom date format: `dd-mm-yyyy` using **Format Cells > Custom**

---

### 5. 🏷️ Renamed Column Headers
- Converted all headers to **lowercase**
- Replaced **spaces with underscores**
- Removed any special characters
- Renamed `listed_in` → `genres` for clarity

#### Final Column Headers:
show_id, type, title, director, cast, country_cleaned, date_added, release_year, rating_cleaned, duration, genres, description


---

## 📁 Deliverables
- ✅ Cleaned dataset file: `netflix_titles_cleaned.xlsx`
- ✅ `README.md` file documenting all cleaning steps

---

## ✨ Done by: *Aditya Kankarwal*

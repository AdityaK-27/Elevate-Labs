Task - 4
# 📊 Netflix Data Analysis using SQL

📅 Date: 27-06-2025  
📂 Task: SQL for Data Analysis

---

## 📝 Project Overview
This project analyzes Netflix's content catalog using SQL to extract valuable business insights. By querying a structured dataset of Movies and TV Shows, the goal was to answer key business questions and practice advanced SQL techniques like subqueries, joins, views, and indexing.

## ✅ Project Objectives

- Explore Netflix’s content trends by type, country, release year, and genre
- Identify top-performing countries, directors, and actors
- Create SQL queries using `GROUP BY`, `ORDER BY`, `ILIKE`, `JOIN`, and `VIEW`
- Classify content using keyword-based filtering
- Demonstrate query optimization techniques via indexing

---

## 📦 Dataset

The data for this project is sourced from the Kaggle dataset:

- **Dataset Link:** [Kaggle Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows?resource=download)

---

## 🧰 Tools & Technologies Used

- **PostgreSQL** (for writing and executing queries)
- **GitHub** (for code, screenshots, and documentation)
- **Kaggle** (for dataset)

---

## Schema

```sql
CREATE TABLE netflix
(
	show_id	VARCHAR(6),
	type 	VARCHAR(10),
	title 	VARCHAR(150),
	director	VARCHAR(208),
	casts	VARCHAR(1000),
	country	VARCHAR(150),	
	date_added VARCHAR(50),
	release_year INT,
	rating VARCHAR(10),
	duration VARCHAR(15),
	listed_in VARCHAR(100),
	description VARCHAR(250)
);
```

## Business Problems and Solutions

### 1. Count the Number of Movies vs TV Shows

```sql
SELECT
	type,
	COUNT(*) AS total_content
FROM netflix
GROUP BY type;
```
**Objective:** Determine the distribution of content types on Netflix.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/1.png)

### 2. Find the Most Common Rating for Movies and TV Shows

```sql
SELECT
	type,
	rating
FROM
(
SELECT
	type,
	rating,
	COUNT(*),
	RANK() OVER(PARTITION BY type ORDER BY COUNT(*) DESC) as ranking
FROM netflix
GROUP BY 1,2
) as t1
WHERE 
	ranking = 1;
```
**Objective:** Identify the most frequently occurring rating for each type of content.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/2.png)

### 3. List All Movies Released in a Specific Year (e.g., 2020)

```sql
SELECT * FROM netflix
WHERE 
	type= 'Movie'
	AND
	release_year=2020;
```

**Objective:** Retrieve all movies released in a specific year.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/3.png)

### 4. Find the Top 5 Countries with the Most Content on Netflix

```sql
SELECT
	TRIM(UNNEST(STRING_TO_ARRAY(country, ','))) as new_country,
	-- we have multiple country names in a single cell
	-- use string to array to resolve this and UNNEST them to get each country in different cell(not distinct yet)
	-- trim is used to remove any whitespaces to the left or right (otherwise these usually cause error is in finding distinct values)
	COUNT(show_id) as total_content
FROM netflix
GROUP BY 1
ORDER BY 2 DESC
LIMIT 5;
```

**Objective:** Identify the top 5 countries with the highest number of content items.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/4.png)

### 5. Identify the Longest Movie

```sql
SELECT
	title,
	SUBSTRING(duration, 1, position('m' in duration)-1):: int duration
FROM netflix
WHERE 
	type='Movie'
	AND
	duration IS NOT NULL
ORDER BY 2 DESC
LIMIT 1;
```

**Objective:** Find the movie with the longest duration.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/5.png)

### 6. Find Content Added in the Last 5 Years

```sql
SELECT 
	*
FROM netflix
WHERE 
	TO_Date(date_added, 'Month DD, YYYY') >= CURRENT_DATE- INTERVAL '5 years'
```

**Objective:** Retrieve content added to Netflix in the last 5 years.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/6.png)

## 📌 Advanced SQL Features
### 7. JOIN with Ratings Description Table

```sql
-- Create ratings_info table
CREATE TABLE ratings_info (
    rating_code VARCHAR(10),
    description TEXT
);

-- Sample data
INSERT INTO ratings_info (rating_code, description) VALUES
('TV-MA', 'Mature Audience'),
('TV-14', 'Teens 14 and older'),
('PG', 'Parental Guidance Suggested'),
('R', 'Restricted'),
('G', 'General Audience');

-- JOIN query
SELECT 
    n.title,
    n.type,
    n.rating,
    r.description
FROM netflix n
LEFT JOIN ratings_info r
    ON n.rating = r.rating_code
LIMIT 10;
```
**Objective**: Enrich Netflix data with human-readable rating descriptions using a LEFT JOIN.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/7.png)

### 8. Create a VIEW for Recently Added Content

```sql
CREATE VIEW recent_5_years_content AS
SELECT 
    *
FROM netflix
WHERE 
    TO_DATE(date_added, 'Month DD, YYYY') >= CURRENT_DATE - INTERVAL '5 years';
```
**Objective**: Reuse logic by creating a view for recent content analysis.

#### Example Usage:

```sql
SELECT 
    type, COUNT(*) 
FROM recent_5_years_content
GROUP BY type;
```
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/8.png)

### 9. Optimization with Indexing (Comment Only)

#### To improve performance on frequently searched columns, indexing can be applied as follows:

```sql
-- Recommended Indexes
CREATE INDEX idx_director ON netflix (director);
CREATE INDEX idx_country ON netflix (country);
CREATE INDEX idx_rating ON netflix (rating);
```
#### This can speed up filtering and JOIN operations involving these columns.

### 10. Find All Movies/TV Shows by Director 'Rajiv Chilaka'

```sql
SELECT
	*
FROM netflix
WHERE director ILIKE '%Rajiv Chilaka%';
```

**Objective:** List all content directed by 'Rajiv Chilaka'.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/10.png)

### 11. List All TV Shows with More Than 5 Seasons

```sql
--Solution 1 (Using SUBSTRING Function)
SELECT 
	*
FROM netflix
WHERE
	type='TV Show'
	AND
	SUBSTRING(duration, 1,2):: INT > 5;

--Solution 2 (Using SPLIT_PART Function)
SELECT 
	*
FROM netflix
WHERE
	type='TV Show'
	AND
	SPLIT_PART(duration, ' ', 1):: INT > 5;
```

**Objective:** Identify TV shows with more than 5 seasons.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/11.png)

### 12. Count the Number of Content Items in Each Genre

```sql
--Solution 1(Using UNNEST and STRING_TO_ARRAY Functions)
SELECT
	UNNEST(STRING_TO_ARRAY(listed_in, ',')) AS genre,
	COUNT(show_id) as total_content
FROM netflix
GROUP BY 1;
```

**Objective:** Count the number of content items in each genre.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/12.png)

### 13.Find each year and the average numbers of content release in India on netflix. return top 5 year with highest avg content release !

```sql
--Subquerry return the value of total content by India over the years
--Count(*) return the total content added in that particular year (Look at Group By carefully)
SELECT
	EXTRACT(YEAR FROM TO_DATE(date_added, 'Month DD, YYYY')) as year,
	COUNT(*) AS yearly_content,
	ROUND(COUNT(*)::NUMERIC/(SELECT COUNT(*) FROM netflix WHERE country='India'):: NUMERIC * 100, 2) as avg_content
FROM netflix
WHERE 
	country='India'
GROUP BY 1;
```

**Objective:** Calculate and rank years by the average number of content releases by India.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/13.png)

### 14. List All Movies that are Documentaries

```sql
SELECT 
	*
FROM netflix
WHERE
	type='Movie'
	AND
	listed_in ILIKE '%documentaries%';
```

**Objective:** Retrieve all movies classified as documentaries.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/14.png)

### 15. Find All Content Without a Director

```sql
SELECT 
	*
FROM netflix
WHERE 
	director IS NULL;
```

**Objective:** List content that does not have a director.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/15.png)

### 16. Find How Many Movies Actor 'Salman Khan' Appeared in the Last 10 Years

```sql
SELECT
	COUNT(*) as Salman_movies
FROM netflix
WHERE 
	casts ILIKE '%Salman Khan%'
	AND
	release_year > EXTRACT(YEAR FROM CURRENT_DATE) -10;

```

**Objective:** Count the number of movies featuring 'Salman Khan' in the last 10 years.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/16.png)

### 17. Find the Top 10 Actors Who Have Appeared in the Highest Number of Movies Produced in India

```sql
SELECT
	UNNEST(STRING_TO_ARRAY(casts,',')) as Actors,
	COUNT(*) AS Number_of_Movies
FROM netflix
WHERE
	type='Movie'
	AND
	Country ILIKE '%India'
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;
```
**Objective:** Identify the top 10 actors with the most appearances in Indian-produced movies.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/17.png)

### 18. Categorize the content based on the presence of the keywords 'kill' and 'violence' in the description field. Label content containing these keywords as 'Bad' and all other content as 'Good'. Count how many items fall into each category.

```sql
SELECT 
	CASE
	WHEN 
		description ILIKE '%Kill%'
		or
		description ILIKE '%violence%' THEN 'Bad_Content'
		ELSE 'Good_Content'
	END category,
	COUNT(*) as Count_of_each_Category
FROM netflix
GROUP BY 1;
```

**Objective:** Categorize content as 'Bad' if it contains 'kill' or 'violence' and 'Good' otherwise. Count the number of items in each category.
#### Output:
![Output](https://github.com/AdityaK-27/Elevate-Labs/blob/main/Task-4%3A%20SQL%20for%20Data%20Analysis/18.png)

---

## 🧪 SQL Concepts Demonstrated

- `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`, `HAVING`
- `JOIN` operations (LEFT JOIN with a ratings description table)
- Subqueries using `RANK()` and `WINDOW FUNCTIONS`
- String manipulation: `ILIKE`, `STRING_TO_ARRAY`, `UNNEST`, `SPLIT_PART`
- Creation of SQL `VIEWS`
- Indexing for optimization (commented)

---

## 📊 Key Business Insights

- **More Movies than TV Shows**  
  Netflix favors single-play content over episodic series.

- **Top Ratings:**  
  `TV-MA` and `TV-14` dominate, suggesting a focus on mature audiences.

- **Top Countries for Content:**  
  USA, India, and UK contribute the most titles to the platform.

- **Most Common Genres:**  
  Drama, International Movies, and Comedy top the list.

- **Keyword-Based Categorization:**  
  A basic content sentiment analysis was performed by labeling shows containing "kill" or "violence" as "Bad".

- **Director & Actor Trends:**  
  Queried all content from directors like Rajiv Chilaka, and ranked Indian actors by their number of appearances.

---

## 🧠 Advanced SQL Additions

### 🔹 Join with Ratings Info Table

Enriched data using a `LEFT JOIN` with a `ratings_info` table that explains rating codes like `TV-MA`, `PG`, etc.

### 🔹 SQL View for Recent Additions

Created a `VIEW` named `recent_5_years_content` to analyze titles added in the past 5 years.

### 🔹 Indexing Suggestions

Indexed `director`, `country`, and `rating` fields (commented) to optimize common filter queries.

---

## 📎 Final Deliverables
- ✅ `README.md` – Complete project documentation (this file)

---

✨ Done by: **Aditya Kankarwal**

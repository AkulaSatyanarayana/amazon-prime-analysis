# 🎬 Amazon Prime Content Analysis

![Dashboard](amazon-prime-dashboard.jpg)

## 📌 Project Overview
Analyzed Amazon Prime Video content dataset containing **9,655 titles** across 
**519 genres** from **1920 to 2021** using Python, SQL, and Power BI.

---

## 📊 Dashboard Preview

### Main Dashboard
![Amazon Prime Dashboard](amazon-prime-dashboard.jpg)

### Content by Country
![Amazon Prime Map](amazon-prime-map.jpg)

---

## 🔍 Key Insights
- 📺 **80.82%** of content are TV Shows vs **19.18%** Movies
- 🎭 **Drama** is the most popular genre with **986 titles**
- 👶 **13+ rating** has the highest content with **2,117 titles**
- 🌍 **USA, India & UK** are top content producing countries
- 📈 Content releases **increased sharply after 2000**
- 🎬 Total of **5,771 unique directors** on the platform

---

## 🛠️ Tools & Technologies Used
| Tool | Purpose |
|------|---------|
| Python (Pandas) | Data Cleaning & EDA |
| SQL (MySQL) | Data Extraction & Aggregation |
| Power BI | Dashboard & Visualization |
| Power Query | Data Transformation |
| DAX | KPI Calculations |

---

## 🐍 Python Code Sample
```python
import pandas as pd

# Load dataset
df = pd.read_csv('amazon_prime_titles.csv')

# Data Cleaning
df.dropna(subset=['title', 'type'], inplace=True)
df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')

# Fix inconsistent genre naming
df['listed_in'] = df['listed_in'].str.strip().str.title()

# EDA - Top Genres
top_genres = df['listed_in'].value_counts().head(10)
print(top_genres)
```

---

## 🗄️ SQL Queries Used
```sql
-- Content distribution by country
SELECT country, COUNT(*) AS total_titles
FROM amazon_prime
GROUP BY country
ORDER BY total_titles DESC;

-- Top genres
SELECT listed_in AS genre, COUNT(*) AS total
FROM amazon_prime
GROUP BY listed_in
ORDER BY total DESC
LIMIT 10;

-- Movies vs TV Shows
SELECT type, COUNT(*) AS count
FROM amazon_prime
GROUP BY type;
```

---

## 📈 Results
- Successfully cleaned and standardized **9,655 records**
- Built interactive dashboard with **6 visualizations**
- Enabled dynamic filtering by **release year & country**
- Verified accuracy by cross-checking SQL results with Power BI

---

## 👨‍💻 Author
**Akula Satyanarayana**  
📧 satyanarayanasatya168@gmail.com  
💼 [LinkedIn](https://www.linkedin.com/in/satya-akula-8b7780292)  
🐙 [GitHub](https://github.com/akulasatyanarayana)

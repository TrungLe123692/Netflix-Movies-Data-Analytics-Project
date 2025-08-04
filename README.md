#                                               🎬 Netflix Movies Data Analytics Project  
![Language](https://img.shields.io/badge/Language-Python-red)  
![Visualization](https://img.shields.io/badge/Visualization-Tableau-purple)  
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)  
![Data](https://img.shields.io/badge/Data-Netflix-blue)

> A data-driven analytics and visualization project using Python and Tableau to uncover viewer behavior, content trends, and platform strategy for Netflix.

---

## 1. Overview

This project analyzes over **9,000+ Netflix titles** using Python and Tableau to extract insights into genre distribution, popularity trends, rating behavior, and content evolution over time.

- **Exploratory Data Analysis (EDA)** and **visualization** using `pandas`, `matplotlib`, and `seaborn`  
- **Tableau dashboard** to present interactive charts and genre-country breakdowns  
- Designed for **data analyst** and **BI roles** involving content analytics, media strategy, and trend detection

---

## 2. Business Objectives

### 2.1. Business Problem

Netflix aims to optimize its global content strategy using insights from historical title performance and viewer preferences. This analysis supports:

- Identifying top genres and rating patterns  
- Understanding production trends by country and year  
- Detecting gaps and opportunities in catalog composition

**Key Business Questions:**

- What is the most frequent genre on Netflix?
- What movies had the highest and lowest popularity?
- Which content types dominate the platform?
- Which year had the highest number of releases?
- What countries produce the most Netflix content?

### 2.2. Business Impact

- **Content Strategy Optimization** – Identify top genres and prolific countries for future investment  
- **Marketing Campaign Targeting** – Segment content by type and region for more precise advertising  
- **Catalog Composition Insights** – Understand balance between movies vs. TV shows  
- **Release Trend Forecasting** – Plan seasonal or regional content drops using past patterns

---

## 3. Dataset & Schema

The project combines two datasets with a total of **12+ columns** and **8,800+ rows**, containing metadata about Netflix content and IMDb-related movie attributes.

### 🗃️ Netflix Content Metadata

| Column        | Description                                  | Data Type |
|---------------|----------------------------------------------|-----------|
| show_id       | Unique identifier for each show              | VARCHAR   |
| type          | Indicates if the title is a Movie or TV Show | VARCHAR   |
| title         | Title of the show                            | VARCHAR   |
| director      | Name of the director                         | VARCHAR   |
| cast          | Names of main cast members                   | VARCHAR   |
| country       | Country of origin                            | VARCHAR   |
| date_added    | Date the title was added to Netflix          | DATE      |
| release_year  | Original release year                        | INT       |
| rating        | Age rating (e.g., PG-13, R)                  | VARCHAR   |
| duration      | Length or number of seasons                  | VARCHAR   |
| listed_in     | Genres/categories                           | VARCHAR   |
| description   | Short summary                                | TEXT      |

### 🎞️ Movie Metadata with Ratings

| Column     | Description                             | Data Type |
|------------|-----------------------------------------|-----------|
| name       | Name of the movie                       | VARCHAR   |
| rating     | Content rating (e.g., PG, R, G)         | VARCHAR   |
| genre      | Genre(s) of the movie                   | VARCHAR   |
| year       | Year of release                         | INT       |
| released   | Full release date                       | DATE      |
| score      | IMDb score                              | FLOAT     |
| votes      | Number of IMDb user votes               | INT       |
| director   | Director of the movie                   | VARCHAR   |
| writer     | Screenwriter(s)                         | VARCHAR   |
| star       | Lead actor/actress                      | VARCHAR   |
| country    | Country of origin                       | VARCHAR   |
| budget     | Budget of the movie                     | VARCHAR   |

---

## 4. Python Analysis Workflow

### 4.1. 🧹 Data Loading & Cleaning

- Loaded CSVs using `pd.read_csv()`  
- Inspected data with `.info()`, `.head()`, `.shape()`  
- Used `.describe()` for summary statistics  
- Checked for duplicates using `.duplicated()`  
- Cleaned genres, countries, and nulls for consistency

### 4.2. 📊 Exploratory Data Analysis (EDA)

- Used `.value_counts()` to assess genre and rating frequency  
- Created bar charts, donut plots, and heatmaps using `matplotlib` and `seaborn`  
- Compared vote counts and IMDb scores to identify top/low performers  
- Analyzed year-wise release trends

### 4.3. 📈 Sample Visualizations

- **Genre Frequency Plot**  
- **Vote Count Distribution**  
- **Top & Lowest IMDb Scores by Genre**  
- **Yearly Content Releases**  
- **Content Type Breakdown**

---

## 5. Tableau Dashboard Design

- **Genre Popularity (Bar Chart):**  
  Visualizes the most common genres on Netflix.

- **Rating Distribution (Bar Chart):**  
  Compares age rating breakdowns (e.g., PG-13, R, TV-MA).

- **Content Type (Donut Chart):**  
  Shows proportion of Movies vs TV Shows.

- **Country-wise Title Count (Map):**  
  Displays production origin and distribution by geography.

- **Release Trend (Area Chart):**  
  Highlights the number of titles released each year.

- **Interactive Filters:**  
  Includes dynamic filters for content type, country, and title.

---

## 6. Key Questions Answered

- 🎬 **Most Frequent Genre**: What is the most popular genre in Netflix’s catalog?  
- 🌍 **Top Country Producers**: Which countries have the highest number of movies/shows?  
- 🔝 **Top IMDb Vote**: Which titles have the highest user vote and ratings?  
- 📉 **Lowest Popularity Titles**: What genres are associated with least popular content?  
- 📆 **Most Productive Year**: Which year had the most Netflix releases?

---

## 7. Business Outcomes

- Data-driven support for genre acquisition and production planning  
- Strategic regional investments based on historical country trends  
- Viewer engagement insights to personalize recommendations  
- Improved scheduling for seasonal content drops

---

## 📈 View the Interactive Dashboard

[![View in Tableau Public](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau)](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)  
👉 **[Click here to explore the live Tableau dashboard](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)**  
This dashboard visualizes genre trends, rating distributions, country output, and time-based content patterns for Netflix’s global library.

---

## 📂 Resources

- Python Notebook: [`Python_Netflix_Movie_Data_Analytics_Project.ipynb`](./Python_Netflix_Movie_Data_Analytics_Project.ipynb)  
- Tableau Dashboard: [Tableau Public Link](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)  
- Dataset Source: [Kaggle Netflix Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)

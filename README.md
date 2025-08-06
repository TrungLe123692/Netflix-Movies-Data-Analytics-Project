#                                               🎬 Netflix Movies Data Analytics Project  
![Language](https://img.shields.io/badge/Language-Python-red)  
![Visualization](https://img.shields.io/badge/Visualization-Tableau-purple)  
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)  
![Data](https://img.shields.io/badge/Data-Netflix-blue)

> A data-driven analytics and visualization project using Python and Tableau to uncover viewer behavior, content trends, and platform strategy for Netflix.

---

## 1. Project Overview

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

## 4. Data Analysis & Modeling Techniques

The cleaned dataset was analyzed and modeled using **pandas**, **matplotlib**, **seaborn**, and **scikit-learn** to uncover trends and build predictive insights.

---

## 4. Data Analysis & Modeling Techniques

The cleaned dataset was analyzed and modeled using **pandas**, **matplotlib**, **seaborn**, and **scikit-learn** to uncover trends and build predictive insights.

---

### 4.1 Exploratory Data Analysis (EDA)

- **4.1.1 Univariate Analysis:**
  - Explored the distribution of key variables using `value_counts()` and `countplot()`:
    - Content **Type** (Movies vs TV Shows)
    - **Rating** categories (TV-MA, PG, etc.)
    - Top contributing **Countries**

- **4.1.2 Time Series Analysis:**
  - Extracted `Year Added` and `Month Added` from `Date Added`
  - Created **line charts** to visualize content uploads over time and detect growth patterns

- **4.1.3 Genre Insights:**
  - Split multi-genre entries using `.str.split(', ')` and normalized them with `.explode()`
  - Used **bar plots** to display top genres and frequency of occurrence

- **4.1.4 Duration Patterns:**
  - Extracted numeric runtime values from the `Duration` column using regex
  - Visualized content length using **boxplots** and **histograms**

- **4.1.5 Geographic Distribution:**
  - Identified top 10 content-producing countries with `value_counts()`
  - Used **bar charts** to show country-level contribution to the Netflix library

---

### 4.2 Model Training & Evaluation (scikit-learn)

- **4.2.1 Data Splitting:**
  - Split dataset using `train_test_split()` with an 80/20 ratio
  - Applied `random_state` to ensure reproducibility of results

- **4.2.2 Model Development:**
  - Trained two regression models:
    - **Linear Regression** as a simple baseline
    - **Random Forest Regressor** with 100 estimators for ensemble-based prediction
  - Used one-hot encoded genre features and numeric columns as input variables

- **4.2.3 Prediction & Evaluation:**
  - Made predictions on the test set using `.predict()`
  - Evaluated model performance using:
    - **Mean Squared Error (MSE)**
    - **Mean Absolute Error (MAE)**
    - **R² Score (coefficient of determination)**

- **4.2.4 Performance Visualization:**
  - Used `seaborn.scatterplot()` to compare predicted vs actual values
  - Evaluated model accuracy based on closeness to the 45-degree diagonal line

> ✅ This combined approach of exploratory analysis and predictive modeling provided both descriptive insights and forward-looking intelligence into Netflix’s content trends.

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


## 📈 View the Interactive Dashboard

[![View in Tableau Public](https://img.shields.io/badge/Tableau-Dashboard-blue?logo=tableau)](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)  
👉 **[Click here to explore the live Tableau dashboard](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)**  
This dashboard visualizes genre trends, rating distributions, country output, and time-based content patterns for Netflix’s global library.

---

## 📂 Resources

- Python Notebook: [`Python_Netflix_Movie_Data_Analytics_Project.ipynb`](./Python_Netflix_Movie_Data_Analytics_Project.ipynb)  
- Tableau Dashboard: [Tableau Public Link](https://public.tableau.com/app/profile/your_username_here/viz/NetflixDashboard/Overview)  
- Dataset Source: [Kaggle Netflix Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)

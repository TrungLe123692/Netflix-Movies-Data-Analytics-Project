#                                               🎬 Netflix Movies Data Analytics Project  
![Language](https://img.shields.io/badge/Language-Python-blue) ![Visualization](https://img.shields.io/badge/Visualization-Tableau-red) ![Status](https://img.shields.io/badge/Project-Completed-yellow) ![Data](https://img.shields.io/badge/Data-Netflix-orange)

---

## 1. Project Overview

This project analyzes over **9,000+ Netflix titles** using Python and Tableau to extract insights into genre distribution, popularity trends, rating behavior, and content evolution over time.

- **Exploratory Data Analysis (EDA)** and **visualization** using `pandas`, `matplotlib`, and `seaborn`  
- **Tableau dashboard** to present interactive charts and genre-country breakdowns  
- Designed for **data analyst** and **BI roles** involving content analytics, media strategy, and trend detection

---

## 📂 Resources

- Python Script: [Netflix Movies Python Script](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/Python_Netflix_Movie_Data_Analytics_Project.ipynb)
- Tableau Dashboard: [Netflix Movies Dashboard](https://public.tableau.com/app/profile/trung.le6260/viz/NetflixMoviesDataAnalytics/Summary)
- Dataset Source: [Netflix Movies Dataset](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/mymoviedb.csv)
- Movies Dataset: [Netflix IMDP Movies Dataset](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/netflix_titles%20(1).csv)

---

## 2. Business Objectives

### 2.1. Business Problem

Netflix aims to optimize its global content strategy using insights from historical title performance and viewer preferences. This analysis supports:

- Identifying top genres and rating patterns  
- Understanding production trends by country and year  
- Detecting gaps and opportunities in catalog composition

### 2.2. Key Business Questions

- What is the most frequent genre on Netflix?
- What movies had the highest and lowest popularity?
- Which content types dominate the platform?
- Which year had the highest number of releases?
- What countries produce the most Netflix content?

---

## 3. Dataset & Schema

The project combines two datasets with a total of **12+ columns** and **8,800+ rows**, containing metadata about Netflix content and IMDb-related movie attributes.

🗃️ [Netflix Content Metadata](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/netflix_titles%20(1).csv)

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

🎞️ [Movie Metadata with Ratings](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/mymoviedb.csv)

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

[Project Structure](https://github.com/TrungLe123692/Netflix-Movies-Data-Analytics-Project/blob/main/data_structure) 

<img width="417" height="811" alt="Screenshot 2025-08-10 155431" src="https://github.com/user-attachments/assets/7dfeff9e-606b-454e-8c6d-5aef50001a90" />

---

## 4. Data Analysis & Modeling Techniques

> ✅ The cleaned dataset was analyzed and modeled using **pandas**, **matplotlib**, **seaborn**, and **scikit-learn** to uncover trends and build predictive insights.

---

### 4.1 Exploratory Data Analysis (EDA)

> ✅ This combined approach of exploratory analysis and predictive modeling provided both descriptive insights and forward-looking intelligence into Netflix’s content trends.

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

> ✅ This approach combined baseline linear regression with a random forest model to balance simplicity and predictive power.

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

---
## 5. Python Codes

### 5.1 Data Cleaning

> ✅ This section outlines the end-to-end steps to prepare the Netflix dataset for analysis using Python. These cleaning steps ensure consistent, reliable data for deeper exploration and visualization.

 - **5.1.1 Convert 'Date Added' to datetime**

   - Enables time-based analysis, such as content trends by year and month.

```python
df['Date Added'] = pd.to_datetime(df['Date Added'])
```

- **5.1.2 Extract 'Year Added' and 'Month Added**

   - Adds two new columns for year and month to support trend analysis.

```python
df['Year Added'] = df['Date Added'].dt.year
df['Month Added'] = df['Date Added'].dt.month
```

- **5.1.3 Drop duplicates and irrelevant columns**

  - Removes noise and unnecessary fields like `Show Id` and `Description`.

```python
df.drop_duplicates(inplace=True)
df.drop(['Show Id', 'Description'], axis=1, inplace=True)
```

- **5.1.4 Drop missing values**

  - Removes rows with null values to ensure clean statistical results.

```python
df.dropna(inplace=True)
```

- **5.1.5 Normalize 'Genre' values**

   - Splits multiple genres and explodes them into individual rows for accurate grouping.

```python
df['Genre'] = df['Genre'].str.split(', ')
df = df.explode('Genre')
```

- **5.1.5 Extract duration in minutes**

   - Extracts numeric values from the `Duration` column to allow quantitative comparisons.

```python
df['Minutes'] = df['Duration'].str.extract('(\d+)').astype(float)
```

- **5.1.6. Most Filmed Year**
```python
df['Release_Date'].hist()
plt.title('Release_Date column distribution')
plt.show()
```

<img width="569" height="435" alt="download (4)" src="https://github.com/user-attachments/assets/da44e17a-8109-4bfc-8f0b-9b671a54dc82" />


- **5.1.7. Most Frequent Genre**
```python
df['Genre'].describe()
sns.catplot(y='Genre', data=df, kind='count',
            order=df['Genre'].value_counts().index,
            color='#4287f5')
plt.title('genre column distribution')
plt.show()
```

<img width="505" height="512" alt="download (5)" src="https://github.com/user-attachments/assets/d301bdb3-13f4-44c9-a267-5e80877a403f" />


- **5.1.8. Genres with Gighest Votes**
```python
df['Genre'].describe()
sns.catplot(y='Genre', data=df, kind='count',
            order=df['Genre'].value_counts().index,
            color='#4287f5')
plt.title('genre column distribution')
plt.show()
```

<img width="506" height="512" alt="download (6)" src="https://github.com/user-attachments/assets/6c3c363f-3d76-4094-b68c-ffd047d1b491" />


---


### 5.2 Modeling

> ✅ This section covers the machine learning pipeline built to predict target values (e.g., rating, duration, or popularity) based on structured Netflix data. It includes preprocessing, model training, and evaluation.

- **5.2.1 Import modeling libraries**

   - Essential libraries from `scikit-learn` and others are imported to support regression modeling, evaluation, and visualization.

```python
from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.linear_model import LinearRegression
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import pandas as pd
```

- **5.2.2 Preprocess data for modeling**

   - One-hot encode the `'Genre'` column  
   - Drop irrelevant or non-numeric columns like `'Title'` and `'Description'`  
   - Handle missing values by removing incomplete rows

```python
df_model = df.copy()

# One-hot encoding
df_model = pd.get_dummies(df_model, columns=['Genre'], drop_first=True)

# Drop non-numeric fields
df_model = df_model.drop(['Title', 'Description'], axis=1, errors='ignore')

# Drop rows with missing data
df_model = df_model.dropna()

df_model.head()
```


- **5.2.3 Split dataset into training and testing sets**

   - Splits the preprocessed dataset into 80% training and 20% testing data.

```python
from sklearn.model_selection import train_test_split

X = df_model.drop('TargetColumn', axis=1)  # Replace 'TargetColumn' with your actual target
y = df_model['TargetColumn']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

print(f"Training set size: {X_train.shape[0]} samples")
print(f"Testing set size: {X_test.shape[0]} samples")
```

- **5.2.4 Train and evaluate Linear Regression model**

   - Fits a simple linear model and evaluates its performance using common regression metrics.

```python
lr_model = LinearRegression()
lr_model.fit(X_train, y_train)

y_pred_lr = lr_model.predict(X_test)

# Evaluation
mse_lr = mean_squared_error(y_test, y_pred_lr)
mae_lr = mean_absolute_error(y_test, y_pred_lr)
r2_lr = r2_score(y_test, y_pred_lr)

print(f"Linear Regression MSE: {mse_lr:.2f}")
print(f"Linear Regression MAE: {mae_lr:.2f}")
print(f"Linear Regression R²: {r2_lr:.2f}")
```

- **5.2.5 Train and evaluate Random Forest model**

   - Fits a more robust ensemble model and compares performance against the linear baseline.

```python
rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)

y_pred_rf = rf_model.predict(X_test)

# Evaluation
mse_rf = mean_squared_error(y_test, y_pred_rf)
mae_rf = mean_absolute_error(y_test, y_pred_rf)
r2_rf = r2_score(y_test, y_pred_rf)

print(f"Random Forest MSE: {mse_rf:.2f}")
print(f"Random Forest MAE: {mae_rf:.2f}")
print(f"Random Forest R²: {r2_rf:.2f}")
```

- **5.2.6 Compare model performance**

   - Visually compare predictions vs actual values or display a summary of metrics.

```python
plt.figure(figsize=(8, 5))
sns.scatterplot(x=y_test, y=y_pred_rf)
plt.xlabel('Actual Values')
plt.ylabel('Predicted Values (RF)')
plt.title('Random Forest Predictions vs Actual')
plt.show()
```

## 6. Tableau Dashboard Design

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

## 📂 Resources

- Python Notebook: [Python_Netflix_Movie_Data_Analytics_Project.ipynb](./Python_Netflix_Movie_Data_Analytics_Project.ipynb)  
- Tableau Dashboard: [Tableau Public Link](https://public.tableau.com/app/profile/trung.le6260/viz/NetflixMoviesDataAnalytics/Summary)
- Dataset Source: [Kaggle Netflix Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)

# Netflix Movies Data Analytics Project 
## Business Objective
Netflix is known for its work in data science, AI, and ML, particularly for building strong recommendation models and algorithms that understand customer behavior and patterns. Suppose you are working in a data-driven job role, and you have a dataset of more than 9,000 movies. You need to solve some key business questions to help the company make informed business decisions accordingly.

View my Tableau dashboard: [Netflix Movies Data Analytics Dashboard](https://public.tableau.com/views/NetflixMoviesDataAnalytics/Summary?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## About the Data 
The dataset was obtained from the [Netflix Movies and TV Shows dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows). It contains metadata about Netflix’s content library as of 2021, including details like title, director, cast, country, release year, and genre. The dataset includes 12 columns and over 8,800 rows:

<img width="1333" height="568" alt="Screenshot 2025-07-17 085658" src="https://github.com/user-attachments/assets/896b8fdc-0ca4-4dd5-814b-c50b3b69010f" />

The second dataset is a curated collection of movies with various metadata attributes useful for film analysis, recommendations, and trend exploration that is obtained from [Netflix Movies Info dataset](https://drive.google.com/file/d/1G1w8zvYi8UU-WsXwbbB0ejKB-aqtDz7g/view?usp=sharing) . It includes 12 columns and contains information such as movie names, genres, release year, IMDb ratings, and more:

<img width="1375" height="631" alt="Screenshot 2025-07-17 090217" src="https://github.com/user-attachments/assets/cbce8d91-7211-4b79-96de-494b6d64f2e6" />

## I took the follwing steps for my Python script
### Data Loading 
Import Dataset: Loaded `mymoviedb.csv` using `pd.read_csv()`

### Exploratory Data Analysis (EDA)
1. Inspect Data Structure: Used `.info()`, `.head()`, and `.shape()` to understand dataset size and shema.
2. Summary Statistics: Ran `.describe()` to view mean, count, std dev, etc., for numerical columns.
3. Genre Analysis: Explored the `genre` column to understand the types and frequency of genres.
4. Frequency Analysis: Used `.value_counts()` to identify the most common values in specific columns.

### Data Cleaning 
Duplicate Detection: Identified and reviewed duplicate rows using `.duplicated().`

### Data Visualization 
Seaborn Plot: Created a statistical visualization using `seaborn` and `matplotib` to answer some key business questions.

## I took follwing steps for my Tableau dashboard
1. Loaded and cleaned the Netflix dataset in Tableau.
2. Created visuals: map by country, bar chart of ratings, donut chart by type, genre bar chart, area chart by year.
3. Added filters for title and type.
4. Styled with a dark theme, red highlights, and interactive layout.

## Key Questions to Answer 
1. What is the most frequent genre of movies released on Netflix?
2. Which has highest votes in vote avg column?
3. What movie got the highest popularity? what's its genre?
4. What movie got the lowest popularity? what's its genre?
5. Which year has the most filmmed movies?

## Business Impacts 
`Content Strategy Optimization:` Identifies top-performing genres and countries to guide future content investments and licensing decisions.

`Targeted Marketing Insights:` Helps tailor marketing campaigns by understanding viewer preferences by region, genre, and rating.

`Catalog Composition Analysis:` Highlights the balance between movies and TV shows, supporting decisions on content mix and user engagement strategies.

`Release Trend Forecasting:` Reveals historical content release trends, enabling better planning for seasonal releases or content drops.









  

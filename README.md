# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

# **Netflix Movies and TV Shows Analysis**

## Overview

This project analyses Netflix's content catalogue using data analytics and visualisation techniques. The analysis includes data cleaning, feature engineering, and dashboard creation to uncover insights about Netflix's content strategy, regional distribution, and temporal trends.

The project demonstrates the complete data analytics pipeline from raw data extraction to business intelligence dashboards, providing actionable insights for content strategy and market analysis.

## Objectives  

1. **Data Cleaning & Preparation**: Process and clean the Netflix dataset to ensure data quality and consistency for analysis.

2. **Feature Engineering**: Create meaningful features from existing data to enhance analytical capabilities and dashboard insights.

3. **Exploratory Data Analysis**: Uncover patterns, trends, and insights in Netflix's content catalogue across different dimensions.

4. **Dashboard Development**: Build interactive Power BI dashboards to visualise key metrics and provide actionable business intelligence.

## Data

**Source**: `data/netflix_titles.csv` (Original dataset from Kaggle)  
**Cleaned Dataset**: `data/netflix_cleaned.csv`  
**Feature-Engineered Dataset**: `data/netflix_with_features.csv`

**Key Features**:
- **show_id**: Unique identifier for each title
- **type**: Content type (Movie or TV Show)
- **title**: Name of the movie or TV show
- **director**: Director(s) of the content
- **cast**: Main cast members
- **country**: Country/countries of production
- **date_added**: Date when content was added to Netflix
- **release_year**: Year of original release
- **rating**: Content rating (PG, R, TV-MA, etc.)
- **duration**: Runtime in minutes (movies) or seasons (TV shows)
- **listed_in**: Genres/categories
- **description**: Brief content description

## Business Requirements

We will be focusing on 4 key requirements:

1. **Analyse temporal patterns in Netflix content acquisition** - Investigate how content addition trends have evolved over time and identify seasonal patterns
2. **Examine regional content distribution and strategy** - Explore how Netflix's content varies across different countries and regions
3. **Investigate content duration preferences and patterns** - Analyse movie runtime trends and TV show season patterns to understand viewer preferences
4. **Identify content categorisation and genre insights** - Examine genre distribution, popularity trends, and content classification patterns for strategic planning

## Hypotheses and Validation

**H1: More content is added in December than other months**
- **Validation**: Count content additions by month using `month_added` feature
- **Visual**: Bar chart showing content count per month
- **Test**: Compare December count vs other months

**H2: Movies are longer than 90 minutes on average**
- **Validation**: Calculate mean duration for movies using `duration_mins` 
- **Visual**: Histogram of movie durations with 90-minute reference line
- **Test**: Check if mean > 90 minutes

**H3: US produces the most content on Netflix**
- **Validation**: Count content by country using `country` column
- **Visual**: Horizontal bar chart of top 10 countries by content count
- **Test**: Verify US has highest count

Alternative country hypotheses you could use:

**H3a: International content makes up more than 30% of Netflix catalogue**
- **Validation**: Count US vs non-US content using `country` column
- **Visual**: Pie chart showing US vs International content split
- **Test**: Check if non-US content > 30%

**H3b: India and United Kingdom are in the top 5 content-producing countries**
- **Validation**: Rank countries by content count using `country` column
- **Visual**: Bar chart of top 10 countries by content volume
- **Test**: Verify India and UK appear in top 5 positions

**H3c: More than 15% of content involves multiple countries**
- **Validation**: Use `has_multiple_countries` feature (True/False values)
- **Visual**: Donut chart showing single vs multi-country productions
- **Test**: Check if multi-country content > 15%

**H4: Drama is the most popular genre on Netflix**
- **Validation**: Split and count individual genres from `listed_in` column
- **Visual**: Bar chart showing top 10 genres by frequency
- **Test**: Check if Drama appears most frequently across all content

Alternative genre hypotheses you could use:

**H4a: Comedy appears in more than 20% of all Netflix content**
- **Validation**: Count how many titles contain "Comedy" in `listed_in` column
- **Visual**: Pie chart showing Comedy vs Other genres percentage
- **Test**: Check if Comedy content > 20% of total

**H4b: International content makes up more than half of Netflix genres**
- **Validation**: Count titles with "International" in `listed_in` column
- **Visual**: Donut chart showing International vs Domestic genre split
- **Test**: Verify International genres > 50%

**H4c: TV content has more diverse genres than Movies**
- **Validation**: Compare unique genre count between Movies and TV Shows in `listed_in`
- **Visual**: Side-by-side bar chart of genre diversity by content type
- **Test**: Check if TV Shows have more unique genres than Movies

## How to use this repo

* Set the `.python-version` Python version to a [Heroku-22](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version that closest matches what you used in this project.
* The project can be deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. At the **Deploy** tab, select **GitHub** as the deployment method.
3. Select your repository name and click **Search**. Once it is found, click **Connect**.
4. Select the branch you want to deploy, then click **Deploy Branch**.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click the button **Open App** at the top of the page to access your App.
6. If the slug size is too large, then add large files not required for the app to the `.slugignore` file.

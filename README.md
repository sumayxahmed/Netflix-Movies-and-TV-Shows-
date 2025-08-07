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

To support the business objectives outlined above, the following testable hypotheses were developed:

### 1. Temporal Patterns in Content Acquisition
**Hypothesis 1**: Netflix has significantly increased the number of TV Shows added to its platform in recent years compared to Movies.
- **Validation**: Compare TV Show vs Movie additions by year using `year_added` and `type` columns
- **Visual**: Stacked bar chart showing content type distribution over time
- **Test**: Calculate yearly ratios and identify if TV Show proportion has increased
✅ *This supports identifying time-based trends in content strategy.*

### 2. Regional Content Distribution  
**Hypothesis 2**: The United States accounts for the majority of Netflix content, followed by India and the United Kingdom.
- **Validation**: Count content by country using `country` column and rank top producers
- **Visual**: Horizontal bar chart of top 10 countries by content volume
- **Test**: Verify US has highest count and India/UK are in top 3 positions
✅ *This helps explore geographic priorities in content distribution.*

### 3. Content Duration Preferences
**Hypothesis 3**: Most Netflix movies have a runtime between 90 and 120 minutes.
- **Validation**: Filter movies using `type` column and analyse `duration` distribution
- **Visual**: Histogram of movie durations with 90-120 minute range highlighted
- **Test**: Calculate percentage of movies within 90-120 minute range
✅ *This helps identify optimal movie lengths based on existing trends.*

### 4. Genre Insights
**Hypothesis 4**: Drama and International content are the most common genres on Netflix.
- **Validation**: Split and count individual genres from `listed_in` column
- **Visual**: Bar chart showing top 10 genres by frequency
- **Test**: Verify Drama and International appear in top 2 most frequent genres
✅ *This supports understanding genre popularity and content planning.*

## How to use this repo

* Set the `.python-version` Python version to a [Heroku-22](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version that closest matches what you used in this project.
* The project can be deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. At the **Deploy** tab, select **GitHub** as the deployment method.
3. Select your repository name and click **Search**. Once it is found, click **Connect**.
4. Select the branch you want to deploy, then click **Deploy Branch**.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click the button **Open App** at the top of the page to access your App.
6. If the slug size is too large, then add large files not required for the app to the `.slugignore` file.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

# **Netflix Movies and TV Shows Analysis**

Netflix Movies and TV Shows Analysis is a comprehensive data analysis tool designed to streamline data exploration, analysis, and visualisation of Netflix's content catalogue. The tool supports multiple data analysis techniques and provides actionable business intelligence for both technical and non-technical stakeholders in content strategy and market analysis.

## Table of Contents

1. [Dataset Content](#dataset-content)
2. [Business Requirements](#business-requirements)
3. [User Stories](#user-stories)
4. [Hypothesis and How to Validate](#hypothesis-and-how-to-validate)
5. [Project Plan](#project-plan)
6. [The Rationale to Map Business Requirements to Data Visualizations](#the-rationale-to-map-business-requirements-to-data-visualizations)
7. [Analysis Techniques Used](#analysis-techniques-used)
8. [Ethical Considerations](#ethical-considerations)
9. [Dashboard Design](#dashboard-design)
10. [Unfixed Bugs](#unfixed-bugs)
11. [Development Roadmap](#development-roadmap)
12. [Deployment](#deployment)
13. [Main Data Analysis Libraries](#main-data-analysis-libraries)
14. [Credits](#credits)
15. [Acknowledgements](#acknowledgements)

## Dataset Content

The project utilises the Netflix Movies and TV Shows dataset from Kaggle, containing detailed information about Netflix's content catalogue. The dataset has been carefully selected with a reasonable size to avoid exceeding repository limits while providing comprehensive insights.

**Source**: `data/netflix_titles.csv` (Original dataset from Kaggle - 8,807 records)  
**Processed Datasets**: 
- `data/netflix_cleaned.csv` (Cleaned and validated data)
- `data/netflix_with_features.csv` (Feature-engineered dataset)
- `data/machine_learning.csv` (ML predictions and enhanced features)

**Key Dataset Features**:
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

The project addresses four strategic business requirements for Netflix content analysis:

1. **Analyse temporal patterns in Netflix content acquisition** - Investigate how content addition trends have evolved over time and identify seasonal patterns for strategic planning.

2. **Examine regional content distribution and strategy** - Explore how Netflix's content varies across different countries and regions to optimise global content strategy.

3. **Investigate content duration preferences and patterns** - Analyse movie runtime trends and TV show season patterns to understand viewer preferences and content optimisation.

4. **Identify content categorisation and genre insights** - Examine genre distribution, popularity trends, and content classification patterns for strategic content acquisition and recommendation system enhancement.

## User Stories

The Netflix Content Analysis project serves multiple stakeholder groups with distinct analytical needs and objectives:

### Executive Leadership
- **As a Chief Content Officer**, I want to understand global content acquisition trends so that I can make strategic decisions about budget allocation and content investment priorities.
- **As a Regional Director**, I want to see content distribution by country so that I can identify market gaps and expansion opportunities in underrepresented regions.
- **As a VP of Strategy**, I want to analyse content type trends (Movies vs TV Shows) so that I can align our content portfolio with viewer preferences and industry shifts.

### Content Acquisition Team
- **As a Content Acquisition Manager**, I want to see the most popular genres so that I can prioritise negotiations with content creators in high-demand categories.
- **As a Market Analyst**, I want to understand movie duration preferences so that I can provide guidance on optimal content length for acquisitions.
- **As a Content Strategist**, I want to identify content rating distributions so that I can ensure balanced portfolio coverage across different audience segments.

### Data Science & Analytics Team
- **As a Data Scientist**, I want to access machine learning predictions for content classification so that I can automate content categorisation processes.
- **As a Business Analyst**, I want to validate statistical hypotheses about content trends so that I can provide evidence-based recommendations to stakeholders.
- **As an Analytics Engineer**, I want to understand feature importance in content prediction models so that I can optimise data collection and processing pipelines.

### Product & Recommendation Teams
- **As a Recommendation Algorithm Developer**, I want to understand genre popularity patterns so that I can improve content suggestion accuracy for users.
- **As a Product Manager**, I want to see temporal content trends so that I can plan feature releases aligned with content availability patterns.
- **As a UX Researcher**, I want to analyse content characteristics so that I can design better content discovery interfaces.

### International Operations
- **As an International Expansion Manager**, I want to see country-wise content distribution so that I can develop localisation strategies for new markets.
- **As a Regional Content Manager**, I want to understand local vs international content ratios so that I can balance global appeal with regional preferences.

- **User Acceptance Criteria**
- **Dashboard Performance**: All visualisations load within 3 seconds for optimal user experience
- **Data Accuracy**: Statistical analyses include confidence intervals and significance testing for reliable insights
- **Interactive Functionality**: Users can filter by date ranges, countries, and content types for customised analysis
- **Export Capability**: Key insights and data can be exported for presentations and further analysis
- **Mobile Responsiveness**: Dashboard accessible on various devices for on-the-go decision making

## Hypothesis and How to Validate

To support the business objectives outlined above, the following testable hypotheses were developed and validated through statistical analysis:

### 1. Temporal Patterns in Content Acquisition
**Hypothesis 1**: Netflix has significantly increased the number of TV Shows added to its platform in recent years compared to Movies.
- **Validation Method**: Two-proportion z-test comparing TV Show vs Movie proportions between early years (≤2015) and recent years (>2015)
- **Statistical Test**: Two-proportion z-test using `proportions_ztest` from statsmodels
- **Null Hypothesis (H₀)**: No significant difference in TV Show proportion over time
- **Alternative Hypothesis (H₁)**: Significant increase in TV Show proportion in recent years
- **Visualisation**: Dual-line chart showing Movies vs TV Shows additions over time (2008-2021)
- **Results**: Statistical validation with p-value < 0.05 confirming significant increase
- **Implementation**: `jupyter_notebooks/hypothesis-testing.ipynb`

### 2. Regional Content Distribution  
**Hypothesis 2**: The United States accounts for the majority (>50%) of Netflix content, followed by India and the United Kingdom in the top 3.
- **Validation Method**: Proportion test for US majority + descriptive analysis for top 3 ranking
- **Statistical Test**: One-proportion z-test for US majority using `proportions_ztest`
- **Null Hypothesis (H₀)**: US does not account for majority OR India/UK not in top 3
- **Alternative Hypothesis (H₁)**: US accounts for >50% AND India/UK are in top 3
- **Visualisation**: Horizontal bar chart of top 10 countries by content volume
- **Results**: Statistical validation of geographic content distribution patterns
- **Implementation**: Country frequency analysis with proportion testing

### 3. Content Duration Preferences
**Hypothesis 3**: Most Netflix movies have a runtime between 90 and 120 minutes.
- **Validation Method**: One-proportion z-test to check if >50% of movies fall in 90-120 minute range
- **Statistical Test**: One-proportion z-test using `proportions_ztest`
- **Null Hypothesis (H₀)**: ≤50% of movies are in 90-120 minute range
- **Alternative Hypothesis (H₁)**: >50% of movies are in 90-120 minute range
- **Visualisation**: Histogram of movie duration categories with 90-120 minute range highlighted
- **Results**: Statistical evidence for optimal movie length validation
- **Implementation**: Duration filtering and proportion calculation for movies only

### 4. Genre Insights
**Hypothesis 4**: Drama and International content are the most common genres on Netflix.
- **Validation Method**: Chi-square goodness of fit test for genre frequency analysis
- **Statistical Test**: Chi-square test using `chisquare` from scipy.stats
- **Null Hypothesis (H₀)**: Drama and International are NOT the top 2 most common genres
- **Alternative Hypothesis (H₁)**: Drama and International content are the most common genres
- **Visualisation**: Bar chart showing top 10 individual genres by frequency
- **Results**: Genre frequency ranking with statistical significance testing
- **Implementation**: Genre parsing from `listed_in` column with frequency analysis

### 4. Genre Insights
**Hypothesis 4**: Drama and International content are the most common genres on Netflix.
- **Validation Method**: Genre frequency analysis by parsing `listed_in` column
- **Statistical Test**: Frequency analysis and chi-square goodness of fit test
- **Visualisation**: Bar chart showing top 10 genres by frequency
- **Results**: Statistical validation of genre popularity rankings
✅ *Supports understanding genre popularity for content planning.*

## Project Plan

The project follows a comprehensive data science methodology encompassing the complete analytics pipeline:

### High-Level Analysis Steps:
1. **Data Collection & Assessment** - Acquired Netflix dataset and performed initial data quality assessment
2. **Data Cleaning & Preparation** - Implemented robust data cleaning processes to ensure data integrity
3. **Feature Engineering** - Created meaningful derived features to enhance analytical capabilities
4. **Exploratory Data Analysis** - Conducted comprehensive statistical analysis and hypothesis testing
5. **Machine Learning Implementation** - Developed predictive models for content classification and rating prediction
6. **Dashboard Development** - Created interactive Power BI dashboards for business intelligence
7. **Results Interpretation** - Translated analytical findings into actionable business insights

### Data Management Throughout Analysis:
- **Collection**: Systematic data ingestion with validation checkpoints
- **Processing**: Automated data cleaning pipelines with error handling
- **Analysis**: Version-controlled Jupyter notebooks with reproducible analysis steps
- **Interpretation**: Statistical validation of findings with confidence intervals and significance testing

### Research Methodology Selection:
**Quantitative Approach**: Chosen for its ability to provide statistically robust insights from large datasets, enabling evidence-based business recommendations.

**Statistical Testing**: Implemented hypothesis testing framework to validate business assumptions with statistical significance.

**Machine Learning**: Applied supervised learning techniques for predictive analytics and automated content classification.

## The Rationale to Map Business Requirements to Data Visualizations

| Business Requirement | Data Visualisation | Rationale |
|----------------------|-------------------|-----------|
| **Temporal Content Patterns** | Time series charts, stacked bar charts | Effectively shows trends over time and enables pattern identification for strategic planning |
| **Regional Distribution Analysis** | Geographic maps, horizontal bar charts | Provides clear geographic insights and country-wise content comparison for market strategy |
| **Duration Preference Analysis** | Histograms, box plots | Statistical distribution visualisation enables optimal content length identification |
| **Genre Insights** | Bar charts, treemaps, pie charts | Hierarchical and comparative visualisation of genre popularity for content acquisition strategy |

## Analysis Techniques Used

### Statistical Analysis Methods:
- **Descriptive Statistics**: Central tendency, dispersion, and distribution analysis
- **Hypothesis Testing**: Chi-square tests, proportion tests, confidence interval analysis
- **Correlation Analysis**: Relationship identification between content characteristics

### Machine Learning Techniques:
- **Random Forest Classifier**: Content type prediction (Movie vs TV Show) with 85%+ accuracy
- **Logistic Regression**: Rating category prediction with multi-class classification
- **Feature Engineering**: Created 10+ derived features for enhanced predictive capability

### Data Structure and Justification:
The analysis was structured using a layered approach:
1. **Foundation Layer**: Data cleaning and validation
2. **Feature Layer**: Engineering meaningful derived variables
3. **Analysis Layer**: Statistical testing and hypothesis validation
4. **Prediction Layer**: Machine learning model implementation
5. **Visualisation Layer**: Business intelligence dashboard creation

### Data Limitations and Alternative Approaches:
- **Missing Data**: Implemented robust imputation strategies for categorical and numerical variables
- **Categorical Complexity**: Used advanced encoding techniques for multi-valued categorical features
- **Scale Differences**: Applied standardisation and normalisation for machine learning models
- **Temporal Gaps**: Addressed missing temporal data through interpolation and trend analysis

### Generative AI Tools Usage:
- **Ideation**: Used AI assistance for feature engineering ideas and statistical test selection
- **Design Thinking**: AI-supported approach to dashboard layout and user experience optimisation  
- **Code Optimisation**: Leveraged AI for code review, performance optimisation, and best practices implementation

## Ethical Considerations

### Data Privacy and Legal Compliance:
- **Public Dataset**: Utilised publicly available Netflix dataset from Kaggle with appropriate licensing
- **No Personal Data**: Analysis focused on content metadata without user personal information
- **Attribution**: Proper crediting of data sources and methodologies

### Bias and Fairness Issues:
- **Geographic Bias**: Acknowledged potential Western content bias in dataset
- **Temporal Bias**: Considered historical data limitations when making future recommendations
- **Genre Bias**: Recognised potential classification bias in genre categorisation

### Mitigation Strategies:
- **Transparent Methodology**: Documented all analytical decisions and limitations
- **Statistical Validation**: Used robust statistical testing to minimise interpretation bias
- **Multiple Perspectives**: Considered various analytical approaches to validate findings

## Dashboard Design

### Dashboard Architecture:
The Power BI dashboard provides comprehensive Netflix content analysis through interactive visualizations designed for strategic decision-making:

#### Netflix Content Overview Dashboard
- **KPI Cards**: 
  - Total Netflix Titles: 8,808
  - Global Markets: 751
  - Movies: 6,131
  - TV Shows: 2,676
- **Content Acquisition Growth**: Line chart showing Netflix content acquisition trends (2008-2021) with dramatic growth starting around 2014
- **Top Countries by Content Volume**: Horizontal bar chart displaying content distribution with United States leading, followed by India, United Kingdom, and other major markets
- **Content Type Trends**: Dual-line chart comparing Movies vs TV Shows additions over time (2008-2021), showing the shift toward TV show content in recent years
- **Content Rating Distribution**: Pie chart breaking down content by rating categories (TV-MA, TV-14, R, PG-13, etc.)
- **Most Popular Content Genres**: Comprehensive bar chart showing genre frequency with International Movies and Dramas leading the distribution
- **Movie Length Distribution**: Histogram displaying movie duration categories (Long, Standard, Very Long, Short) with Standard length being most common
- **Interactive Filters**: Year range slider (2008-2021) and country selection filters for dynamic analysis
- **Target Audience**: Content strategy teams, executives, and market analysts

### Key Dashboard Insights:
- **Growth Pattern**: Exponential content growth from 2014-2019 with peak acquisition around 2018-2019
- **Geographic Strategy**: Strong US content dominance with significant international diversification
- **Content Mix Evolution**: Clear shift from movie-focused to balanced movie/TV show strategy
- **Genre Focus**: International content and Drama categories drive content portfolio strategy

### Technical and Non-Technical Communication:
- **Executive Level**: High-level KPIs with clear business impact metrics and trend visualisation
- **Strategic Teams**: Detailed content distribution analysis with country and genre breakdowns
- **Operational Teams**: Actionable insights with specific recommendations and implementation guidance

## Due to limitations with the version of PowerBI being used, a link cannot be provided, however, a file is available in Dashboards folder labelled Netflix-Movies-and-TV-Shows

## Unfixed Bugs

### Framework Limitations:
- **Power BI Connector**: Occasional timeout issues with large dataset refresh, mitigated through data chunking
- **Jupyter Memory**: Large dataset processing limitations addressed through efficient data handling techniques

### Known Issues and Rationale:
- **Date Parsing Edge Cases**: Some non-standard date formats remain unparsed (affects <1% of data)
  - **Rationale**: Cost-benefit analysis showed minimal impact on overall analysis accuracy
- **Country Multi-Assignment**: Content with multiple country assignments handled through primary country selection
  - **Rationale**: Preserves data integrity while enabling clear geographic analysis

### Knowledge Gaps Addressed:
- **Advanced Statistical Testing**: Enhanced understanding through additional research and implementation
- **Power BI Advanced Features**: Continuous learning approach with incremental feature adoption
- **Machine Learning Optimisation**: Applied cross-validation and hyperparameter tuning techniques

## Development Roadmap

### Challenges Faced and Solutions:
1. **Data Quality Issues**: Implemented comprehensive data validation and cleaning pipeline
2. **Feature Engineering Complexity**: Developed systematic approach to meaningful feature creation
3. **Statistical Validation**: Enhanced understanding of appropriate statistical tests for business hypotheses
4. **Dashboard Performance**: Optimised data models and implemented efficient visualisation techniques

### Next Skills and Tools to Learn:
- **Advanced ML Techniques**: Deep learning for content recommendation systems
- **Real-time Analytics**: Stream processing for live content analysis
- **Advanced Visualisation**: D3.js for custom interactive visualisations
- **Cloud Deployment**: Azure or AWS for scalable analytics solutions

## Deployment

### Heroku Deployment
The App live link is: [Your Heroku App URL]

The project was deployed to Heroku using the following steps:
1. Set the `runtime.txt` Python version to a Heroku-22 stack currently supported version
2. Log in to Heroku and create an App
3. From the Deploy tab, select GitHub as the deployment method
4. Select your repository name and click Search. Once found, click Connect
5. Select the branch you want to deploy, then click Deploy Branch
6. The deployment process should happen smoothly if all deployment files are functional
7. Click the button Open App on the top of the page to access your App
8. If the slug size is too large, add large files not required for the app to the `.slugignore` file

## Main Data Analysis Libraries

### Core Analytics Libraries:
- **Pandas**: Used extensively for data manipulation, cleaning, and transformation throughout the analysis pipeline
- **NumPy**: Implemented for numerical computations and statistical calculations in hypothesis testing
- **Matplotlib & Seaborn**: Created comprehensive statistical visualizations and exploratory data analysis plots
- **Scikit-learn**: Implemented machine learning models including Random Forest Classifier and Logistic Regression

### Example Usage:
```python
# Pandas for data manipulation
df_cleaned = pd.read_csv('data/netflix_cleaned.csv')
content_by_year = df_cleaned.groupby(['year_added', 'type']).size().unstack()

# Scikit-learn for machine learning
from sklearn.ensemble import RandomForestClassifier
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)
```

### Specialised Libraries:
- **Jupyter Notebooks**: Interactive development environment for iterative analysis and hypothesis testing
- **Power BI**: Business intelligence dashboard creation and interactive visualisation development

## Credits

### Content
- **ChatGPT**: Supported with code guidance, data exploration ideas, markdown writing, and error troubleshooting
- **GitHub Copilot**: Assisted with syntax and repetitive code blocks during Python scripting
- **Kaggle**: Netflix Movies and TV Shows dataset https://www.kaggle.com/datasets/shivamb/netflix-shows/code?datasetId=434238
- **Code Institute**: For project structure and guidance 

## Acknowledgements

Special thanks to the Code Institute Data Analytics program for providing the foundational knowledge and project structure guidance that enabled this comprehensive Netflix content analysis project.

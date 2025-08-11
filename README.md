# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

# **Netflix Movies and TV Shows Analysis**

Netflix Movies and TV Shows Analysis is a comprehensive data analysis tool designed to streamline data exploration, analysis, and visualisation of Netflix's content catalogue. The tool supports multiple data analysis techniques and provides actionable business intelligence for both technical and non-technical stakeholders in content strategy and market analysis.

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

2. **Examine regional content distribution and strategy** - Explore how Netflix's content varies across different countries and regions to optimize global content strategy.

3. **Investigate content duration preferences and patterns** - Analyse movie runtime trends and TV show season patterns to understand viewer preferences and content optimization.

4. **Identify content categorisation and genre insights** - Examine genre distribution, popularity trends, and content classification patterns for strategic content acquisition and recommendation system enhancement.

## Hypothesis and How to Validate

To support the business objectives outlined above, the following testable hypotheses were developed and validated through statistical analysis:

### 1. Temporal Patterns in Content Acquisition
**Hypothesis 1**: Netflix has significantly increased the number of TV Shows added to its platform in recent years compared to Movies.
- **Validation Method**: Statistical analysis comparing TV Show vs Movie additions by year using `year_added` and `type` columns
- **Statistical Test**: Chi-square test for independence and proportion analysis
- **Visualization**: Stacked bar chart showing content type distribution over time
- **Results**: Validated through hypothesis testing in `jupyter_notebooks/hypothesis-testing.ipynb`
✅ *Supports identifying time-based trends in content strategy.*

### 2. Regional Content Distribution  
**Hypothesis 2**: The United States accounts for the majority of Netflix content, followed by India and the United Kingdom.
- **Validation Method**: Statistical analysis of content distribution by country using `country` column
- **Statistical Test**: Proportion test and descriptive statistics
- **Visualization**: Horizontal bar chart of top 10 countries by content volume
- **Results**: Statistical validation confirms geographic content priorities
✅ *Helps explore geographic priorities in content distribution strategy.*

### 3. Content Duration Preferences
**Hypothesis 3**: Most Netflix movies have a runtime between 90 and 120 minutes.
- **Validation Method**: Statistical analysis of movie duration distribution using `type` and `duration` columns
- **Statistical Test**: Descriptive statistics and confidence interval analysis
- **Visualization**: Histogram of movie durations with 90-120 minute range highlighted
- **Results**: Statistical evidence supports optimal movie length identification
✅ *Identifies optimal movie lengths based on existing content trends.*

### 4. Genre Insights
**Hypothesis 4**: Drama and International content are the most common genres on Netflix.
- **Validation Method**: Genre frequency analysis by parsing `listed_in` column
- **Statistical Test**: Frequency analysis and chi-square goodness of fit test
- **Visualization**: Bar chart showing top 10 genres by frequency
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

| Business Requirement | Data Visualization | Rationale |
|----------------------|-------------------|-----------|
| **Temporal Content Patterns** | Time series charts, stacked bar charts | Effectively shows trends over time and enables pattern identification for strategic planning |
| **Regional Distribution Analysis** | Geographic maps, horizontal bar charts | Provides clear geographic insights and country-wise content comparison for market strategy |
| **Duration Preference Analysis** | Histograms, box plots | Statistical distribution visualization enables optimal content length identification |
| **Genre Insights** | Bar charts, treemaps, pie charts | Hierarchical and comparative visualization of genre popularity for content acquisition strategy |

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
5. **Visualization Layer**: Business intelligence dashboard creation

### Data Limitations and Alternative Approaches:
- **Missing Data**: Implemented robust imputation strategies for categorical and numerical variables
- **Categorical Complexity**: Used advanced encoding techniques for multi-valued categorical features
- **Scale Differences**: Applied standardization and normalization for machine learning models
- **Temporal Gaps**: Addressed missing temporal data through interpolation and trend analysis

### Generative AI Tools Usage:
- **Ideation**: Used AI assistance for feature engineering ideas and statistical test selection
- **Design Thinking**: AI-supported approach to dashboard layout and user experience optimization  
- **Code Optimization**: Leveraged AI for code review, performance optimization, and best practices implementation

## Ethical Considerations

### Data Privacy and Legal Compliance:
- **Public Dataset**: Utilized publicly available Netflix dataset from Kaggle with appropriate licensing
- **No Personal Data**: Analysis focused on content metadata without user personal information
- **Attribution**: Proper crediting of data sources and methodologies

### Bias and Fairness Issues:
- **Geographic Bias**: Acknowledged potential Western content bias in dataset
- **Temporal Bias**: Considered historical data limitations when making future recommendations
- **Genre Bias**: Recognized potential classification bias in genre categorization

### Mitigation Strategies:
- **Transparent Methodology**: Documented all analytical decisions and limitations
- **Statistical Validation**: Used robust statistical testing to minimize interpretation bias
- **Multiple Perspectives**: Considered various analytical approaches to validate findings

## Dashboard Design

### Dashboard Architecture:
The Power BI dashboard consists of multiple interconnected pages designed for different stakeholder needs:

#### Page 1: Executive Summary Dashboard
- **KPI Cards**: Total content count, movies vs TV shows ratio, average content age
- **Time Series Chart**: Content addition trends over years
- **Geographic Map**: Global content distribution visualization
- **Target Audience**: C-level executives and strategic decision makers

#### Page 2: Content Analysis Deep Dive
- **Duration Analysis**: Movie runtime distribution and TV show season analysis
- **Genre Breakdown**: Interactive treemap of genre popularity
- **Rating Distribution**: Content rating category analysis
- **Filter Controls**: Year, country, content type, and genre filters
- **Target Audience**: Content acquisition and strategy teams

#### Page 3: Predictive Analytics Dashboard
- **ML Model Results**: Content type prediction accuracy and feature importance
- **Rating Prediction**: Automated content rating classification results
- **Feature Impact Analysis**: Statistical significance of content characteristics
- **Target Audience**: Data science and analytics teams

#### Page 4: Regional Strategy Dashboard
- **Country Performance**: Content volume by region with drill-down capability
- **Market Analysis**: Temporal trends by geographic regions
- **Content Gap Analysis**: Identification of underrepresented regions
- **Target Audience**: International expansion and regional strategy teams

### Technical and Non-Technical Communication:
- **Executive Level**: High-level KPIs with clear business impact metrics
- **Technical Teams**: Detailed statistical analysis with confidence intervals and significance testing
- **Operational Teams**: Actionable insights with specific recommendations and implementation guidance

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
- **Machine Learning Optimization**: Applied cross-validation and hyperparameter tuning techniques

## Development Roadmap

### Challenges Faced and Solutions:
1. **Data Quality Issues**: Implemented comprehensive data validation and cleaning pipeline
2. **Feature Engineering Complexity**: Developed systematic approach to meaningful feature creation
3. **Statistical Validation**: Enhanced understanding of appropriate statistical tests for business hypotheses
4. **Dashboard Performance**: Optimized data models and implemented efficient visualization techniques

### Next Skills and Tools to Learn:
- **Advanced ML Techniques**: Deep learning for content recommendation systems
- **Real-time Analytics**: Stream processing for live content analysis
- **Advanced Visualization**: D3.js for custom interactive visualizations
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

### Specialized Libraries:
- **Jupyter Notebooks**: Interactive development environment for iterative analysis and hypothesis testing
- **Power BI**: Business intelligence dashboard creation and interactive visualization development

## Credits

### Content Sources:
- **Dataset**: Netflix Movies and TV Shows Dataset from [Kaggle](https://www.kaggle.com/shivamb/netflix-shows)
- **Statistical Methods**: Hypothesis testing methodologies from statistical analysis best practices
- **Machine Learning Techniques**: Implementation guidance from scikit-learn documentation and best practices

### Technical Implementation:
- **Data Cleaning Techniques**: Adapted from pandas documentation and data science best practices
- **Statistical Testing**: Methodology from academic statistical analysis resources
- **Dashboard Design**: Power BI visualization best practices and user experience guidelines

### Educational Resources:
- **Code Institute**: Data Analytics program curriculum and project structure guidance
- **Statistical Analysis**: Academic resources for hypothesis testing and validation methodologies
- **Machine Learning**: Industry best practices for model development and evaluation

## Acknowledgements

Special thanks to the Code Institute Data Analytics program for providing the foundational knowledge and project structure guidance that enabled this comprehensive Netflix content analysis project.

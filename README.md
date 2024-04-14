# <a name="top"></a>Linear Regression Project
![]()

***
[[Project Description](#project_description)]
[[Project Planning](#planning)]
[[Key Findings](#findings)]
[[Data Dictionary](#dictionary)]
___


## <a name="project_description"></a>Project Description:
Using the data science pipeline to practice with regression. In this repository you will find everything you need to replicate this project. This project is a OLS regression challenge that finds key features of lung cancer mortality rate and uses them to predict it with the least amount of error.

[[Back to top](#top)]

***
## <a name="planning"></a>Project Planning: 
[[Back to top](#top)]

### Project Outline:
- Data Ingestion:-
Implemented a class IngestData to handle data ingestion. Defined a method get_data to read the CSV file and return it as a DataFrame.
- Data Preprocessing:-
Identified and deleted constant columns using find_constant_columns and delete_constant_columns functions. Detected columns with a small number of unique values using find_columns_with_few_values function. Removed duplicate rows using find_duplicate_rows and delete_duplicate_rows functions. Dropped columns with more than 50% missing values and filled remaining missing values with the mean of the column using drop_and_fill function.
- Feature Engineering:-
Transformed specific columns from string representations into numerical features using bin_to_num and cat_to_col functions. One-hot encoded categorical features using the one_hot_encoding function.
- Exploratory Data Analysis (EDA):-
Conducted EDA to explore the data, identify missing values, outliers, and understand the distribution of features. Handled missing values, outliers, and other data anomalies as necessary.
- Building Regression Model:-
Loaded the preprocessed data. Implemented functions for correlation analysis among numeric features, linear regression model building, and identifying significant variables. Trained the linear regression model using sm.OLS from the statsmodels library. Identified significant variables based on p-values.Refined the model by training it only on significant variables. Evaluated the model's performance using metrics like R-squared, adjusted R-squared, and examined the summary statistics.

### Project goals: 
- My goal is to find key features of lung cancer mortality rate and use them to predict it with the least amount of error.


### Target variable:
- The target variable for this project is deathrate.

### Initial questions:
- Where are the correlations in the data?
- Is there a relationship between Deathrate and Incidence Rate?
- Is Deathrate and Binned Income related?
- Is there a relationship between Deathrate and Poverty Percent?
- Is there a relationship between Deathrate and Median Age?
- Does a specific age bin have affect the deathrate?
- How many people that died from cancer were diagnosed?

## <a name="findings"></a>Key Findings:
[[Back to top](#top)]

- Only 1/3 of the people diagnosed actually died.
- The Mid-Aged bin has a slightly higher average deathrate then young or old does.
- The red binned [22640, 34218.1] income has more counties with extreme levels of deathrate.
- The blue binned (61494.5, 125635] income has a majority of their counties below the average deathrate. 


***

## <a name="dictionary"></a>Data Dictionary  
[[Back to top](#top)]

### Data Used

- (a): years 2010-2016
- (b): 2013 Census Estimates
---
| Attribute | Definition | Data Type |
| ----- | ----- | ----- |
| TARGET_deathRate| Dependent variable. Mean per capita (100,000) cancer mortalities(a) | float64 |
| avgAnnCount| Mean number of reported cases of cancer diagnosed annually(a) | float64 |
| avgDeathsPerYear| Mean number of reported mortalities due to cancer(a) | int64 |
| incidenceRate| Mean per capita (100,000) cancer diagoses(a) | float64 |
| medianIncome| Median income per county (b) | int64 |
| popEst2015| Population of county (b) | int64 |
| povertyPercent| Percent of populace in poverty (b) | float64 |
| studyPerCap| Per capita number of cancer-related clinical trials per county (a) | float64 |
| binnedInc| Median income per capita binned by decile (b) | object |
| MedianAge| Median age of county residents (b) | float64 |
| MedianAgeMale| Median age of male county residents (b) | float64 |
| MedianAgeFemale| Median age of female county residents (b) | float64 |
| Geography| County name (b) | object |
| AvgHouseholdSize| Mean household size of county (b) | float64 |
| PercentMarried| Percent of county residents who are married (b) | float64 |
| PctNoHS18_24| Percent of county residents ages 18-24 highest education attained: less than high school (b) | float64 |
| PctHS18_24| Percent of county residents ages 18-24 highest education attained: high school diploma (b) | float64 |
| PctSomeCol18_24| Percent of county residents ages 18-24 highest education attained: some college (b) | float64 |
| PctBachDeg18_24| Percent of county residents ages 18-24 highest education attained: bachelor's degree (b) | float64 |
| PctHS25_Over| Percent of county residents ages 25 and over highest education attained: high school diploma (b) | float64 |
| PctBachDeg25_Over| Percent of county residents ages 25 and over highest education attained: bachelor's degree (b) | float64 |
| PctEmployed16_Over| Percent of county residents ages 16 and over employed (b) | float64 |
| PctUnemployed16_Over| Percent of county residents ages 16 and over unemployed (b) | float64 |
| PctPrivateCoverage: Percent of county residents with private health coverage (b) | float64 |
| PctPrivateCoverageAlone| Percent of county residents with private health coverage alone (no public assistance) (b) | float64 |
| PctEmpPrivCoverage| Percent of county residents with employee-provided private health coverage (b) | float64 |
| PctPublicCoverage| Percent of county residents with government-provided health coverage (b) | float64 |
| PctPubliceCoverageAlone| Percent of county residents with government-provided health coverage alone (b) | float64 |
| PctWhite| Percent of county residents who identify as White (b) | float64 |
| PctBlack| Percent of county residents who identify as Black (b) | float64 |
| PctAsian| Percent of county residents who identify as Asian (b) | float64 |
| PctOtherRace| Percent of county residents who identify in a category which is not White, Black, or Asian (b) | float64 |
| PctMarriedHouseholds| Percent of married households (b) | float64 |
| BirthRate| Number of live births relative to number of women in county (b) | float64 |
| AgeBin| MedianAge binned into 3 parts, young, mid-aged, old | category |
***

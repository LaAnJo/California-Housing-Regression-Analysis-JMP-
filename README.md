# California-Housing-Regression-Analysis-JMP-
Introduction and Problem Statement

The primary focus of this project is to build, evaluate, and interpret regression models for a continuous response variable using JMP statistical software. Specifically, the goal is to predict Median House Value in California based on a set of demographic, housing, and geographic characteristics.

Housing prices are influenced by multiple interacting factors such as income levels, housing density, population characteristics, and proximity to major cities and the coastline. Understanding how these factors relate to house values provides a meaningful and realistic context for applying multiple linear regression techniques.

Source of Data

The dataset used in this project is the California Housing dataset, originally derived from the 1990 California Census and later augmented with additional geographic distance variables.

Source: Kaggle

Link: https://www.kaggle.com/datasets/fedesoriano/california-housing-prices-data-extra-features

The dataset contains housing-related and demographic information for districts across California and is well-suited for regression analysis due to its large sample size, predominantly continuous variables, and clear real-world interpretation.

Dataset Description

Number of observations: 20,640

Number of variables: 14

The dataset is cross-sectional in nature and does not include any time-based variables. All observations represent housing characteristics measured at a single point in time. No missing values were present in the dataset.

Target (Response) Variable

Median_House_Value (Y)

Type: Continuous

Description: Median house value (USD) for a given California district

This variable spans a wide range of values and represents a natural continuous outcome, making it appropriate for regression modeling. The objective is to predict this variable using relevant explanatory variables.

Predictor (Explanatory) Variables

A total of 13 predictor variables were selected based on domain knowledge and exploratory analysis:

Variable Name	Type	Description
Median_Income	Continuous	Median household income
Median_Age	Continuous	Median age of houses
Tot_Rooms	Continuous	Total number of rooms
Tot_Bedrooms	Continuous	Total number of bedrooms
Population	Continuous	Total population
Households	Continuous	Number of households
Latitude	Continuous	Latitude of district
Longitude	Continuous	Longitude of district
Distance_to_coast	Continuous	Distance to nearest coastline (km)
Distance_to_LA	Continuous	Distance to Los Angeles (km)
Distance_to_SD	Continuous	Distance to San Diego (km)
Distance_to_SJ	Continuous	Distance to San Jose (km)
Distance_to_SF	Continuous	Distance to San Francisco (km)
Justification of Variable Selection

The selected predictors provide independent and meaningful information about housing prices and do not trivially define the response variable. Together, they capture multiple dimensions influencing house values:

Economic factors: Median_Income

Housing stock characteristics: Median_Age, Tot_Rooms, Tot_Bedrooms

Population and household structure: Population, Households

Geographic location: Latitude, Longitude

Proximity effects: Distances to coastline and major cities

Exploratory Data Analysis (EDA)

EDA was conducted using the Distribution and Correlation platforms in JMP to understand variable behavior prior to modeling.

Key Findings

Median_House_Value: Right-skewed with high-value outliers and large variability

Median_Income: Moderately right-skewed; expected strong predictor

Tot_Rooms, Tot_Bedrooms, Population, Households: Strong right skewness

Latitude & Longitude: Reflect California’s geographic clustering

Distance variables: Right-skewed; capture proximity effects

Correlation Highlights

Median_Income vs Median_House_Value: Strong positive correlation (≈ 0.69)

Distance_to_coast: Meaningful negative correlation

Room, population, and household variables: Evidence of multicollinearity

These findings motivated the use of formal model selection and validation.

Data Partitioning

To evaluate model performance, the data were split into training and validation sets using JMP.

Training: ~80%

Validation: ~20%

A validation indicator column was created using a random uniform assignment and assigned the Validation role in JMP’s Fit Model platform.

Regression Modeling Approach

Response Distribution: Normal

Link Function: Identity

Model Type: Multiple Linear Regression

Estimation Method: Standard Least Squares

Validation Strategy: Validation Column

This setup establishes a baseline interpretable regression model with formal performance evaluation.

Model Performance
Initial Model (With Validation)

R² (Training): 0.648

R² (Validation): 0.640

RASE (Training): 68,349

RASE (Validation): 69,836

The similarity between training and validation metrics indicates good generalization and minimal overfitting.

Key Interpretations

Median_Income: Strongest positive predictor

Distance_to_coast: Negative effect (closer to coast → higher values)

Geographic variables: Capture spatial price patterns

Population & households: Density and structure effects

All predictors were statistically significant (p < 0.0001).

Outlier Analysis
Motivation

Diagnostic plots identified a small number of high-leverage and high-residual observations that could disproportionately affect model estimates.

Updated Model (After Outlier Removal)

Observations: 20,574

R²: 0.653

Adjusted R²: 0.652

RMSE: 67,599

Findings

Slight improvement in fit and error

Coefficient signs and magnitudes remained stable

Variable importance rankings unchanged

This indicates the model is robust and not driven by a small number of extreme observations.

Final Model Selection

The refined regression model (after outlier removal) was selected as the final model due to:

Improved predictive performance

Stable coefficients

Consistent interpretation

Strong validation behavior

Conclusion and Recommendations

This project successfully demonstrates a complete regression modeling workflow using JMP, including EDA, correlation analysis, model estimation, validation, diagnostics, and interpretation.

Key conclusions:

The final model explains approximately 65% of the variability in median house values

Median income is the most influential predictor

Geographic location and proximity to cities and the coastline significantly affect prices

Results are stable and robust to outlier removal

Future Work

Potential extensions include:

Nonlinear transformations

Interaction effects

Alternative models such as regression trees or ensemble methods

Overall, this project provides meaningful insights into the factors influencing California housing prices while demonstrating sound regression modeling practice.

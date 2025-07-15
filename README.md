# Used Car Price Prediction (Ford F-150)

## Project Overview

This project aims to identify the key factors influencing the price of used Ford F-150 trucks using a the Used cars price dataset . The analysis focuses specifically on Ford F-150s to understand their unique pricing dynamics. The goal is to provide actionable insights to a used car dealership client to help them optimize their inventory and pricing strategies.

The project follows the CRISP-DM framework, covering the stages of Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, and Deployment.

## Dataset

The dataset used in this project is a subset of a larger dataset . It contains information on approximately 426,000 used cars, with a focus on Ford F-150 vehicles for this specific analysis. The data includes various attributes such as:

- Price
- Year
- Odometer reading
- Condition
- Cylinders
- Fuel type
- Title status
- Transmission
- Drive type
- Size
- Type
- Paint color
- State
- Manufacturer
- Model
- Region
- VIN

## Analysis and Modeling

The analysis involved:

- **Data Cleaning and Preparation:** Handling missing values, outliers, and transforming categorical variables using techniques like one-hot encoding and label encoding (for ordered categories like condition).
- **Feature Engineering:** Creating new features such as `label_name` based on order of model trims price and `cylinder_count` and `drive_count` by extracting numerical information from string columns.
- **Exploratory Data Analysis (EDA):** Visualizing data distributions and correlations to understand relationships between variables and the target variable (price).
- **Model Selection and Training:** Building and evaluating several regression models, including:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Lasso Regression with Feature Selection

GridSearchCV was used to tune hyperparameters (specifically polynomial degree and regularization alpha values) and cross-validation was employed to ensure robust model performance.

## Key Findings

The evaluation of the models, primarily using Root Mean Squared Error (RMSE), showed that all models performed similarly, with Test RMSE values around $4600 - $4800. The Lasso with Feature Selection model showed a slightly lower test RMSE.

The analysis of model coefficients from the Lasso with Feature Selection model revealed the following key price drivers for used Ford F-150s:

- **Year:** Newer trucks are significantly more expensive.
- **Odometer:** Higher mileage strongly decreases the price.
- **Trim Level (`label_name`):** Higher trim levels are associated with higher prices.
- **Drive Type (`drive_count`):** Trucks with 4-wheel drive tend to have higher prices.
- **Title Status:** Rebuilt and salvage titles negatively impact the price.
- **Condition (`condition_label`):** The condition of the truck also positively impacts the price.


## Recommendations for the Dealership

Based on the findings, the following recommendations are provided to the used car dealership:

1. **Prioritize Newer, Lower-Mileage F-150s:** These vehicles have the strongest positive impact on price and should be a focus for inventory acquisition.
2. **Stock Popular Trim Levels:** Understand regional demand for specific F-150 trims as they influence pricing.
3. **Consider the Drive Type:** Acquire 4x4 F-150s if your market has a high demand for them.
4. **Be Mindful of Title Status:** Account for the lower market value of vehicles with rebuilt or salvage titles when purchasing and pricing.
5. **Assess and Highlight Vehicle Condition:** Since better condition positively influences price, accurately assessing and marketing the condition of your inventory is important.

## Next Steps and Further Recommendations

Based on this analysis, the following next steps and recommendations are proposed:

- **Expand Analysis to Other Models:** Apply the same analysis and modeling approach to other popular car models in the dataset to provide a comprehensive understanding of price drivers across different vehicle types.
- **Enrich Dataset with Trim and Base Price Information:** Investigate the possibility of adding detailed car trim information and their corresponding base prices (as new cars) to the dataset. This could further improve model accuracy and provide more granular insights into how specific trim levels and their original value influence used car prices.

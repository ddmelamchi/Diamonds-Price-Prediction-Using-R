# Predictive Analytics Model for Diamond Price Estimation Using R

This project focuses on building a predictive model to estimate diamond prices using regression analysis. The goal is to assist both buyers and sellers in determining the appropriate price for diamonds based on specific attributes such as carat, color, and clarity. The analysis leverages publicly available data and applies data science techniques to create an accurate and robust model.

## Dataset
- **Source**: The dataset is publicly available on Kaggle, containing over 53,000 records of diamonds.
- **Subset**: For this analysis, we selected a subset of 1,610 diamonds categorized under the "Fair" cut quality.

### Features:
- **price**: The price of the diamond (in USD).
- **carat**: The weight of the diamond (in carats).
- **color**: Color grading of the diamond (J = worst, D = best).
- **clarity**: Clarity grading of the diamond (I1 = worst, IF = best).
- **x**: Length of the diamond (in mm).
- **y**: Width of the diamond (in mm).
- **z**: Depth of the diamond (in mm).
- **depth**: Total depth percentage.
- **table**: The width of the top of the diamond as a percentage of its widest point.

## Objective
The primary aim is to predict the price of a diamond based on its characteristics. The dataset contains features related to the physical and quality attributes of diamonds, and the objective is to explore how well these features can be used to predict diamond prices.

## Exploratory Data Analysis (EDA)
During the initial EDA phase, the following patterns were observed:
- **Right-skewed price distribution**: Most diamonds are priced lower, with a few high-priced outliers.
- **Carat is strongly correlated with price**: Larger diamonds generally cost more.
- **Color and clarity** also influence diamond prices, though to a lesser degree compared to carat.

Various visualizations such as histograms, box plots, and scatter plots were used to better understand these relationships.

## Model Development
Several regression models were developed to predict diamond prices. The process included:
1. **Multi-Linear Regression (MLR)**: Used to identify key predictors.
2. **Model Selection**: AIC and BIC criteria were used to select the best model by eliminating insignificant predictors.
3. **Log Transformation**: Due to the right-skewed nature of the price distribution, log transformation was applied to both the target variable (price) and the carat feature.

### Final Model:
The final model includes carat, color, and clarity as predictors for diamond price.
- **Model Formula**: `log(price) ~ log(carat) + color + clarity`

### Results and Key Metrics:
- **R² Value**: 0.954 — This means that 95.4% of the variance in diamond prices can be explained by the model’s predictors (carat, color, and clarity).
- **Adjusted R²**: 0.9539 — This metric accounts for the number of predictors and indicates that the model remains highly accurate.
- **RMSE**: The Leave-One-Out Cross-Validation (LOOCV) RMSE for the final model is 0.134, meaning the model’s predictions deviate from the actual values by about 13.4%.

## Conclusions:
- **Carat weight** has the most significant impact on diamond prices.
- **Color and clarity** are important but less influential than carat.
- The model is capable of predicting diamond prices with high accuracy, as shown by the high R² and low RMSE values.

### Limitations:
- Some assumptions of linear regression, such as normality and constant variance, were slightly violated despite transformations.
- The dataset is limited to diamonds with "Fair" cut quality, so the model may not generalize to other cuts.

### Future Work:
- Incorporating additional factors, such as market trends or geographic data, could enhance the model’s accuracy and applicability.
- Machine learning models such as decision trees or random forests could be applied to capture non-linear relationships and further improve prediction accuracy.

## Files in this Repository:
- **Project Report**: Detailed analysis and findings (on the same R Markdown file).
- **Code**: R scripts for EDA, model building, and evaluation.
- **Data sets**: Both the original dataset and the extracted subset.

## How to Run the Code:
1. Clone the repository.
2. `diamonds.csv` is the original dataset downloaded from Kaggle.
3. `final_diamonds.csv` is the subset of 1,610 diamonds categorized under the "Fair" cut quality that we worked with.
4. Install the necessary R packages (`ggplot2`, `dplyr`, `lmtest`, etc.).
5. Run the provided R scripts to reproduce the results.

## Acknowledgments:
- **Dataset**: Provided by Kaggle.
- This project was conducted as part of coursework for the MS in Data Science program.

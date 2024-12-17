# Objectives
## Predict residential property values based on historical data using machine learning techniques.
## Minimize Mean Squared Error (MSE).
## Provide actionable insights and recommendations to CCAO regarding property valuation practices.

# Data Structure
## historic_property_data.csv: containing historical sales prices and property features (50,000 records).
## predict_property_data.csv: containing property features for 10,000 new records.
## codebook.csv: providing descriptons for all variables in the datasets.

# Technical Methodology
## Data Preprocessing
### Data Cleaning
#### Columns with relevant description regarding the codebook were kept.
#### Columns with more than 50% missing values were removed.
#### For numeric columns: missing values were imputed using the median.
#### For categorical columns: missing values were replaced with the mode.
#### For logical columns: missing values were imputed using the most frequent value. 
#### ![Screenshot 2024-12-17 at 12 45 30 PM](https://github.com/user-attachments/assets/9aebd264-16a9-432c-8ea5-f84fcf26900d)
### Exploratory Data Analysis
Summary statistics and a histogram of sale_price were generated to visualize its distribution.
#### ![Screenshot 2024-12-17 at 12 45 43 PM](https://github.com/user-attachments/assets/5d90b896-8204-4899-a325-7057881f4a4c)
## Feature Selection
### High Correlated Variables
#### ![Screenshot 2024-12-17 at 12 46 20 PM](https://github.com/user-attachments/assets/2d75e169-f3c2-4eaa-b121-10efd330d518)
### Lasso Regression
A lambda value was optimized using cross-validation -> non-zero coefficients were extracted to identify the most important features influencing the property values -> a subset of remaining perdictors was used for modeling.
#### ![Screenshot 2024-12-17 at 1 02 06 PM](https://github.com/user-attachments/assets/938d32b7-cea9-46e7-aac8-89c99b0e7867)
## Model Development
### Neural Network Model
#### The model was chosen to capture nonlinear relationship between predictors and property values.
#### Data was scaled to ensure convergence during training.
#### The neural network had 10 hidden units and was trained for 200 iterations.
#### ![Screenshot 2024-12-17 at 12 48 17 PM](https://github.com/user-attachments/assets/6fe1ab70-480f-439c-a903-9f99cd042a4d)
### Prediction
#### Missing valyes in the prediction dataset were imputed using the median for numeric variables and the mode for categorical variables.
#### The neural network model was used to predict property valyes for 10,000 records in the predict_property_data.csv.
#### ![Screenshot 2024-12-17 at 12 48 26 PM](https://github.com/user-attachments/assets/23437f95-c2c1-403f-be8d-1a5261c97b72)
# Recommendations for CCAO
## Adopt Neural Networks 
Compare to traditional methods, neural network handle nonlinear patterns effectively.
## Improve Feature Collection and Data Quality
Ensure that missing values, especially for important features like property condition or square footage, are minimized.

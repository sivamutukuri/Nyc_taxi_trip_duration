# NYC Taxi Trip Duration Prediction

## Introduction

This project aims to predict the duration of taxi trips in New York City using machine learning. The dataset used contains information about taxi trips, including pickup and dropoff locations, timestamps, passenger count, and trip duration. This project uses data exploration, feature engineering, and machine learning modeling to understand patterns and ultimately make predictions.

## Data Exploration and Analysis (EDA)

1. **Data Loading and Inspection:**
   - The dataset is loaded using pandas.
   - Initial data inspection is performed using `head()`, `shape`, `info()`, and `describe()`.
   - Missing values are checked using `isnull().sum()`.

2. **Feature Engineering:**
   - **Geodesic Distance:** `geopy.distance` is utilized to compute distances between pickup and dropoff coordinates, which is an important factor in determining trip duration.
   - **Datetime Features:** Additional features such as month, week, day, and hour are extracted from the pickup timestamp to potentially capture temporal patterns.
   - **Passenger Count and Trip Duration:** The relationship between the number of passengers in the vehicle and trip duration was analyzed using a line plot.

3. **Data Visualization and Insights:**

   ![image](https://github.com/user-attachments/assets/97caead8-1a69-49a8-9367-d1657121a0d7)
   
   ![image](https://github.com/user-attachments/assets/b36b0475-95af-4376-ac54-fdebedcedda2)

   - **Correlation Analysis:** Correlation between features is examined using a heatmap (using `seaborn`). The target variable, trip duration, is identified for correlation analysis and feature importance.
   - The features with the tallest bars (either positive or negative) are the ones that have the strongest influence on trip duration.
     
   ![image](https://github.com/user-attachments/assets/0b16946e-03d9-4d0f-bf22-12a9321b3d10)
     
   - **Skewness Analysis:** Feature skewness analysis is performed, and features exhibiting high skewness are identified. This is important for understanding potential biases in the data.

   ![image](https://github.com/user-attachments/assets/cc80ed3b-d968-4a1c-affb-24818059564d)


   - **Lineplot Visualization:** Used to demonstrate trends like the trip duration distribution concerning the number of passengers on board.
   
   ![image](https://github.com/user-attachments/assets/cf50c66c-ba44-44be-9fc6-78c2e7d7d4ca)

   - **Pointplot Visualization:** Created to compare vendors based on total distance traveled by passenger count.
   
   
   
   
   
  
   

## Feature Engineering

1. **Handling skewness:** Log transformation is applied to the `trip_duration` column to address skewness and improve the predictive power of the model.
2. **Dropping Features:** Some features that contribute less to the prediction or increase dimensionality were dropped such as pickup_longitude and dropoff_longitude, which is expected due to the inclusion of calculated geodesic distance.

## Methods used for Analysis

1. **Data Wrangling and Feature Engineering:** The dataset is manipulated and refined to extract and calculate new features relevant for analysis and model training.
2. **Data visualization:** Several plots and graphs are created, such as heatmaps, line plots, and point plots, that provide visual insights into data patterns and relationships.
3. **Statistical Analysis:** Measures like correlation and skewness are used to quantify relations between variables and discover data characteristics.
4. **Data Preparation and Modeling:** The dataset is prepared, which includes splitting into train and test sets, and scaled for modeling using StandardScaler. Models including Linear Regression, Ridge, KNeighborsRegressor and LightGBM are applied and their performance is evaluated.

## Machine Learning Models

1. Linear Regression: Used as a baseline for other model performance comparison.
2. Ridge Regression: Applied to handle multicollinearity in the dataset, improving the model's overall efficiency.
3. KNeighborsRegressor: A non-linear approach that uses proximity between data points to make predictions. The elbow curve methodology was used to optimize model performance.
4. Light Gradient Boosting Machine (LightGBM): An efficient algorithm to deal with complex relationships in data.

## Model Performance

Based on the evaluation metrics of R-squared and mean squared logarithmic error, LightGBM provided the best results. However, all models are analyzed using cross-validation techniques to improve their reliability and ensure better performance.

## Conclusion

This project demonstrates the application of data science techniques to build predictive models for taxi trip duration. Feature engineering and model selection play significant roles in achieving desirable results. Future work can further explore optimizing models and experimenting with other advanced algorithms.


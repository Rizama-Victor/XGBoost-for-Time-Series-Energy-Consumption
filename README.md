# XGBoost ⚡ for Time Series ⏳ Energy Consumption
This repository contains the implementation of the project titled _"XGBoost for Time Series Energy Consumption"_, at the Department of Mechatronics Engineering (DOME), Federal University of Technology Minna (FUTMinna), Nigeria.

--- 
## 🕒 Project Overview

This project focused on forecasting time-series energy consumption using historical housedold residential usage data recorded at regular intervals. Energy consumption naturally fluctuates based on factors such as time of day, weather, seasonal variations, and human or industrial activity. Understanding these patterns is essential for effective planning in sectors especially residential energy management. 
To support more efficient resource allocation, this project developed a machine learning model using XGBoost to predict future energy usage based on past trends, enabling more informed and proactive energy management decisions.

---

## 🚀 Project Objectives

- To curate and preprocess a clean and structured time-series energy consumption dataset suitable for forecasting.
- To develop and train an XGBoost-based predictive model capable of learning patterns and trends in historical energy usage.
- To assess the model’s performance using appropriate evaluation metrics and optimize it for accurate and reliable energy consumption forecasting.

---

## 🤖 Tools and Technologies Used

| **Tool / Library** | **Purpose in This Project** |
|---------------------|-----------------------------|
| **pandas** | Used for loading, cleaning, and manipulating the time series energy consumption dataset. |
| **re (Regular Expressions)** | Helped in extracting, cleaning, or parsing text-based components within the dataset. |
| **numpy** | Performed numerical operations and handling array-based computations needed for preprocessing. |
| **matplotlib.pyplot** | Visualized patterns and trends in the energy consumption data. |
| **seaborn** | Generated statistical visualizations to improve the appearance of plots. |
| **xgboost** | Was used to build and train the XGBoost model for predicting energy consumption. |
| **sklearn.metrics (MSE, MAE, R²)** | Used to evaluate the model’s performance using regression metrics. |
| **joblib** | Was used to save the trained XGBoost model for later reuse. |
| **scipy.stats** | Helped detect and remove outliers using Z-score during preprocessing. |

## 🔁 Step by Step Procedure

### Data Collection and Preparation

- **Step 1:** A [dataset](Time_Series_Energy_Consumption.csv) of 121273 observations and 2 columns over the course of 14 years was gathered from Kaggle open source dataset platform.

- **Step 2:** To gain a comprehensive overview of the trends in energy consumption over the 14-year period, hourly energy consumption data for each day was plotted against the corresponding datetime. This approach provided a detailed visualization of fluctuations and patterns in energy usage over time.  

- **Step 3:** Using appropriate Python functions, a total of 8 duplicate values were identified and successfully removed from the dataset. To further understand the dataset's structure and detect any missing values, a concise summary of the data was generated. This summary included the total number of columns, the count of non null values (i.e., observations without missing data), and the data types of all columns in the dataset.

- **Step 4:** To enable easy filtering, aggregation and time-based operations, the datetime column was converted to a datetime object in python. It ensured consistent formatting, provided easy access to date components like year or month, and enabled the use of optimized functions. This conversion also supported handling time zones and improved performance during time-related computations. Also, the datetime object was then set as the index, allowing for more efficient slicing, resampling, and analysis of the data based on time intervals.
  
- **Step 5:** To ensure the time series data was correctly organized, all observations were sorted in ascending order based on the datetime column. This arrangement helped to maintain the proper chronological sequence of the data.
  
- **Step 6:** To analyze the energy consumption trend over a specific time period, data from one week (2018-01-01 to 2018-01-07) was visualized in a plot, offering a clear representation of usage patterns during that interval.

- **Step 7:**  To help the model capture underlying trends and patterns in the dataset, avoid oversimplification, and improve prediction accuracy, **feature engineering** was implemented in the creation of new columns. Key features such as "day," "month," "year," and "time" were extracted for each day. Additionally, lagged features representing energy consumption from the previous year were included, along with rolling feature values over 12-hour and 24-hour periods. These steps ensured the model had access to important temporal and consumption-related information.

- **Step 8:** To better understand the statistical summary of the values in the feature-engineered dataset, summary statistics were performed. This provided important details such as the count, which indicates the number of observations; the mean, which is the average value; the standard deviation, which measures how spread out the values are from the mean; the minimum, which is the smallest value; the maximum, which is the largest value; and the quartiles, which divide the data into four equal parts and show the spread and distribution. These statistics offered a clear overview of the dataset's distribution and variability.

- **Step 9:** To identify outliers in the dataset, all feature columns were visualized using box plots. The Z-score outlier handling technique was then applied to remove the detected outliers. The Z-score method calculates how far a data point is from the mean in terms of standard deviations. Data points with Z-scores above a certain threshold are considered outliers and were removed to ensure more accurate analysis.

- **Step 10:** To further understand observe the unique relationship between each feature and the energy consumption, all individual feature columns were visualized using a box plot.

### Train-Test Split
The training set included all energy consumption values up to and including December 31, 2017, while the testing set encompassed observations from January 1, 2018, to the most recent recorded data. 



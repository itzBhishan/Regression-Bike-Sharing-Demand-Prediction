# Regression-Bike-Sharing-Demand-Prediction


# Project Overview: 
This project seeks to utilize regression analysis techniques to forecast the demand for bike sharing services, considering multiple factors. By examining past data and constructing a predictive model, we aim to offer valuable insights and predictions to assist bike sharing companies in making informed decisions and enhancing their operational efficiency.


# Problem Statement: 
Prediction of bike count required at each hour for the stable supply of rental bikes.
General guideline : 
 
# Import Libraries: 
This section includes the necessary libraries and packages imported for data analysis and visualization, data preprocessing, model training, evaluation, and visualization.
# Dataset Loading :
load a data set from a Google Drive location using Google Colab. It mounts Google Drive and then reads the CSV file named "SeoulBikeData.csv" using pd.read_csv() from the pandas library. 
 
.sample is used to display the random rows .
Data.shape is used to display the no of rows and col.The dataset contains 8760 rows and 14 columns’
# Dataset information : 
To provide detailed information about the dataset, we can use the data.info() method. It provides an overview of the columns, their data types, and the number of non-null values.
 
# Duplicate Values : 
The information does not mention any duplicate values in the dataset.
 
# Missing Values/Null Values:
The table shows the number of missing values (null values) in each column of the dataset. There is no missing/ null value in our dataset.
# Visualizing the missing values : 
it creates a heatmap visualization of missing values.The missing values are represented by a distinct color, allowing to identify the presence of missing values in the dataset visually. But there is no missing/ null value in our dataset.
 
What did you know about your dataset?
We have already discuss about this.
 
Data.columns display the coln name
data.describe(include='all') The describe method is used to generate descriptive statistics of the data within the DataFrame.
It would provide summary statistics for each column, including count, mean, standard deviation, minimum, quartiles, and maximum values for numeric columns. For non-numeric columns, it would include the count, unique values, top (most frequent) value, and frequency of the top value.
variables Description this is  Description about each column name.
Unique Values for each variable.

Check Unique Values for each variable.
This loop will iterate over each column in data.columns.tolist() and print a statement indicating the number of unique values in that column.

# Data Wrangling: 
This section focuses on several data transformations and preparations are performed to make the dataset analysis-ready
Convert 'datetime' column to datetime object:
The 'datetime' column is converted from a string format to a datetime object using the pd.to_datetime() function.
Extract date and time features:
Additional features are extracted from the 'datetime' column using the .dt accessor of the datetime object. The 'year', 'month', and 'day', features are created,
The 'day_of_week' feature is also created using the .dayofweek property of the datetime object, which returns the day of the week as an integer (Monday is 0 and Sunday is 6).
Drop unnecessary columns:
The 'datetime' column, which is no longer needed after extracting the date and time features, is dropped from the dataset using the .drop() method with axis=1.
Convert categorical columns to categorical data type:
The 'Seasons', 'Holiday', and 'Functioning Day' columns are converted to the categorical data type using the .astype('category') method.
Check unique values for categorical variables:
The unique values for the categorical variables 'Seasons', 'Holiday', and 'Functioning Day' are printed using the .unique() method.


# What all manipulations have you done and insights you found?
By performing these data transformations, the code prepares the dataset for further analysis by converting datetime-related information into separate features and ensuring appropriate data types for categorical variables.


# Data Visualization,
# Chat 1: Univariate Analysis of Target Variable
**Reason for picking the chart**: histograms provide a visual representation of the distribution of a dataset, helping us understand the underlying patterns, identify outliers, and make informed decisions during data exploration and modeling.

**INSIGHT** : 
Right-skewed distribution of the target variable, bikes fell towards the lower end of the scale, with a few exceptions having a high rental count.
histogram's peak falls between 0 and 1000 bike rentals per hour.
the target variable is not normally distributed,

**Business impact**: by understanding the patterns and characteristics of bike rental demand, the business can make informed decisions to improve its operations and maximize customer satisfaction.




# Chart 2: Count of bike rentals per season
**Reason for picking the chart**: Using a bar plot allows for a clear representation of the distribution of bike rentals across different seasons, making it easier to identify any seasonal trends or differences in rental counts.

**Insights** : 
Bike rentals were highest during the summer season, with autumn, spring, and winter following in descending order.
The season has a substantial influence on bike rental counts, presenting an opportunity to enhance bike rental services based on this understanding.

**Business impact**: 
Positive Impact: when bike rentals are at their highest during the peak season can help businesses plan their marketing initiatives.
In terms of negative development, it's possible that the data analysis's insights will point out areas where the company isn't performing as well as it should.
# Chart 3: Count of bike rentals per month
**Reason for picking chart** : 
Line chat display data points connected by a line. can be used to display trends, patterns, and relationships between two variables over time.

**Insights** :
Bike rentals exhibit a clear seasonal pattern, with higher rates during summer (June, July, and August) and lower rates during winter (December, January, and February).
From March to June, bike rentals steadily increase, 
Although bike rentals are lower during the December holiday season compared to summer, they are still higher than during the winter months.

**Business impact** : 
Analyzing the relationship between weather conditions and rental counts, as well as identifying peak rental times and locations, can help optimize bike rental inventory, staffing, and marketing strategies. This optimization can have a positive impact on the business.

# Chart - 4 visualization code
**Reason for picking chart** : 
Histograms show the distribution of one variable, while scatter plots reveal the relationship between two continuous variables.

**Insight** : 
The histogram shows that the data is skewed to the right, indicating that most of the bike rental counts are lower.
the top-right scatter plot shows a positive correlation between temperature and the number of rented bikes. This means that as the temperature increases, the number of bike rentals also increases.
 bottom-left scatter plot shows a negative correlation between humidity and the number of rented bikes. This means that as the humidity increases, the number of bike rentals decreases.
The bottom-right scatter plot shows a weak negative correlation between wind speed and the number of rented bikes. This means that as wind speed increases, the number of bike rentals slightly decreases.

**Business impact** :
the bike rental company could use this information to optimize its marketing and advertising strategies to attract more customers during certain weather conditions.
# Chart - 5 Count of bike rentals per Hour
**Reason for picking this chart** : bar plot is a good choice when we want to compare the values of a categorical variable (hour of the day) with the values of a numerical variable (rented bike count).

**Insight**: 
The bike rental count is highest during peak commuting hours (8 AM and 7 PM), which is indicative of increased bike usage during typical work or school travel times.
The bike rental count is lowest during non-peak hours (2 AM to 5 AM) as expected.
There is a recurring pattern in the bike rental count, with peaks during morning and evening rush hours and lows during late night/early morning hours.

**Business impact** : This information can assist in identifying the busiest periods for bike rentals, which can be valuable for making staffing, bike maintenance, and pricing decisions.
# Chart 6: Count of bike rentals on holidays or not
**Reason for picking chart** :  bar plot is a good choice when we wants to comparing the values of a categorical variable (holidays and non-holidays) with the values of a numerical variable(rented bike count) .

**Insight** : 
The observation from the chart indicates that bike rentals are more prevalent on regular days rather than on holidays.
This indicates that individuals are more inclined to utilize bike for their daily commutes or leisure pursuits rather than for transportation during holidays.

**Business Impact** :  there is lower demand for bike rentals on holidays, and a business may need to adjust their operations and marketing strategies accordingly.
# Chart 7: Count of bike rentals by Seasons
**Reason for chart** : The Barchart provides a clear and visually appealing way to explore the relationship between weather, time of day, and bike rental demand.

**Insight** : 
There are variations in bike rental patterns among different seasons, with certain seasons experiencing higher rental counts compared to others. The summer season has the highest rental counts.
There are also variations in bike rental patterns throughout the day, with clear peak rental times. The highest rental counts occur at 8 AM and 7 PM.
There could be potential interactions between seasons and different times of the day, where specific seasons are more favorable for bike rentals during specific time periods.

**Business Impact** : By analyzing the differences in bike rental patterns across seasons and times of the day, businesses can optimize their operations, improve customer satisfaction, and maximize revenue potential.
# Chart 8: Count of bike rentals by temperature
**Chart reason** : A line plot is a good choice when you want to visualize the trend or relationship between two continuous variables.

**Insight** : 
There appears to be a positive relationship between temperature and bike rental count, suggesting that higher temperatures are associated with increased bike rentals.
The chart may also identify any outliers or anomalies in the data, such as unusually high or low rental counts associated with specific temperature values.

**Business Impac**t : offering promotions during periods of increase in temperatures to incentivize bike rentals or allocating more resources to locations where temperature has a stronger impact on rental demand.
# Chart 9: Count of bike rentals by humidity
**Why line plot** : Line plots allow us to easily identify trends and patterns in the data.

**Insights** : 
higher humidity levels possibly leading to lower bike rental demand.
A potential threshold effect, once the threshold is crossed, there is a rapid decrease in bike rental demand.

**Business Impact** : the company can make informed decisions to optimize their operations and improve their service, potentially resulting in increased revenue and customer satisfaction
# Chart 10: Count of bike rentals by wind speed
**Why line plot** : Line plots can be used to visualize relationships between two or more variables, such as positive, negative, or no correlation.

**Insight** : 
The relationship between wind speed and bike rentals is not very strong, as indicated by the relatively flat trendline.
a slight decrease in bike rentals as wind speed increases from 0 to around 8 m/s.
There may be some outliers in the data,

**Business Impact**: Businesses should have backup plans and adaptable marketing strategies to handle unfavorable weather conditions. They can offer alternative services and provide weather-related information to customers.This helps maintain customer satisfaction and revenue streams during challenging weather conditions.
# Chart 11: Scatter plot of bike rentals by temperature and humidity
**Why scatter plot** :  to visualize the relationship between two continuous variables, such as temperature and bike rental count.

**Insight** : 
Temperature and bike rentals have a positive relationship, meaning that as temperature increases, bike rental counts also tend to increase.
The strength of the relationship between temperature and bike rentals varies across seasons.
The chart can also highlight outliers or abnormal patterns in the data that may require further exploration.

**Business Impact** : 
during warmer seasons, bike-sharing companies may consider increasing their prices, as demand for bike rentals may be higher.
in certain seasons at specific temperature ranges, bike-sharing companies may adjust their fleet size or marketing strategies to better cater to those seasonal trends.
# Chart 12: Scatter plot of bike rentals by temperature and wind speed
**Why scatter plot**: to visualize the relationship between two continuous variables, such as (Temperature and Wind speed) and the target variable (Bike rentals).

**Insight**: 
Bike rentals are higher at certain temperature and wind speed ranges.
The impact of temperature and wind speed on bike rentals can vary across seasons. In Winter, temperature may have a stronger influence than wind speed, whereas in Summer, wind speed may play a more significant role.

**Business Impact** : 
This knowledge aids in resource allocation, ensuring sufficient bike availability during high-demand periods and optimizing operational efficiency.
during seasons when wind speed is more important, promotional strategies can emphasize the advantages of biking with tailwinds or offer incentives for riding on windy days.

# Chart - 13 Count of bike rentals per month**
**Why bar plot** : Bcz it is a common and powerful visualization tool used to display numerical data across categories or groups.

**Insight** : 
Bike sharing demand is Higher during summer, slightly decreases during the rainy season, and makes constant for the winter season.

**Business impact** : They can focus their marketing efforts on the months with lower rental counts to increase awareness and generate more demand.
# Chart - 14 - Correlation Heatmap
**Why Correlation heatmap** : Heatmaps are commonly used to show correlations between variables.The annotations on the heatmap show the actual correlation coefficients.

**Insight** : 
The Dew Point Temperature and Temperature variables show a strong correlation with each other.
Certain variables exhibit strong positive or negative correlations with the target variable, Rented Bike Count. These variables are influential in predicting bike rental demand.
Some variables display high correlation with each other, indicating redundancy or strong relationships. Removing these variables can reduce multicollinearity in the model.
Certain variables have weak or no correlation with other variables in the dataset, suggesting they have minimal impact on bike rental demand. Removing these variables simplifies the analysis.
# Chart - 15 - Pair Plot
**Why pair plot** : we can visualize the relationships between variables in the dataset and observe how these relationships vary across different hours of the day.
This allows us to detect any patterns or trends between the variables and understand their dependence on the time of day.

**Insight** : 
The relationship between temperature and bike rentals, high
The relationship between humidity and bike rentals, low
The relationship between wind speed and bike rentals low
The differences in these relationships across different seasons.
# Hypothesis Testing
The code provided demonstrates three hypothesis tests performed on the dataset.
1) Hypothesis Test : Comparison of Mean Bike Rentals between Functional and     Non-Functional Days.
-Null hypothesis: There is no significant difference in the mean number of bike rentals between functional and non-functional days.
-Alternative hypothesis: There is a significant difference in the mean number of bike rentals between functional and non-functional days.
-Method: Independent t-test (two-sample t-test) is used to compare the  Mean Bike Rentals between Functional and Non-Functional Days.
-Result: The null hypothesis states that there is no significant difference in the mean number of bike rentals between functional and non-functional days. The alternative hypothesis suggests that there is a significant difference in the mean number of bike rentals between these two types of days.
2)Hypothesis Test : Comparison of Mean Bike Rentals between Holidays and Non-Holidays.
Null hypothesis: The mean number of bike rentals between holidays and non-holidays is not significantly different.
Alternative hypothesis: The mean number of bike rentals between holidays and non-holidays is significantly different.
-Method: Independent t-test (two-sample t-test) is used to compare the Mean Bike Rentals between Holidays and Non-Holidays.
-Result : The p-value is used to interpret the results. The null hypothesis is rejected if the p-value is less than 0.05 (assuming a significance level of 0.05), indicating a significant difference in the mean number of bike rentals between functional and non-functional days. If the p-value is greater than or equal to 0.05, the null hypothesis is not rejected, implying that there is no significant difference in the mean number of bike rentals between functional and non-functional days.
3) Hypothesis Test: Comparison of Mean bike rental during daytime and nighttime.
Null hypothesis: The mean number of bike rentals during daytime and nighttime is not significantly different.
Alternative hypothesis: The mean number of bike rentals during daytime and nighttime is significantly different.
-Method: Independent t-test (two-sample t-test) is used to compare the Mean bike rental during daytime and nighttime.
-Result : The resulting p-value from the t-test is compared to a significance level (usually 0.05) to make a conclusion. If the p-value is less than the significance level, we reject the null hypothesis and conclude that there is a significant difference. Otherwise, if the p-value is greater than or equal to the significance level, we fail to reject the null hypothesis and conclude that there is no significant difference.
# Feature Engineering & Data Pre-processing
The code provided demonstrates several steps of feature engineering.
Handling missing values : There are no missing values in given dataset.
Handling outliers :In this case, the code indicates that there are a few outliers present in the 'Rented Bike Count' variable. However, it states that these outliers will not be removed at the moment, as they could be important data points.
Categorical Encoding : 
One-Hot Encoding: By using one-hot encoding, we transform categorical variables into a binary format, where each category is represented by a separate column. This allows machine learning models to work with categorical data by treating each category as a binary indicator variable.
The resulting dummy variables are binary (1 or 0), indicating the presence or absence of a specific category in the original feature. This encoding preserves the information about the categories without introducing any numerical ordering or bias.
One-hot encoding is especially useful when dealing with categorical variables that do not have an inherent order or when all categories are equally important. It ensures that each category is considered as a separate entity, enabling the model to learn distinct relationships between the categories and the target variable.
4) Feature Manipulation:Feature manipulation plays a crucial role in improving the accuracy and generalizability of machine learning models.
Feature engineering refers to creating new features or transforming existing features to extract more meaningful information. This process leverages domain knowledge, intuition, and data analysis techniques to derive features that can better capture the underlying patterns and relationships in the data.
Removing irrelevant or unnecessary columns from the dataset can be beneficial for the machine learning model. It helps in reducing noise, improving computational efficiency, and focusing on the most relevant features that contribute to the target variable.
5) Feature Selection: It involves selecting the most relevant and informative features from the available set of features. By selecting the right set of features, we can reduce the complexity of the model, improve interpretability, and mitigate the risk of overfitting.
The purpose of this code snippet is to select the top 5 features based on the f_regression scores, which measure the relationship between each feature and the target variable. By selecting the most relevant features, you aim to reduce the risk of overfitting and improve the model's performance.
# Data Transformation : 
By applying this transformation, you can achieve a more symmetric and normalized distribution of the 'Rented Bike Count' variable, which can be beneficial for certain statistical analyses or machine learning models that assume normality or require input variables to have a specific range or distribution.
Handling Imbalanced data :
To address the class imbalance, various techniques can be employed, such as oversampling (generating synthetic examples for minority classes) or undersampling (reducing the number of instances from the majority class). These techniques aim to balance the dataset and provide more representative training data for the model.
the observed class imbalance in the dataset indicates the need for addressing this issue to ensure fair and accurate predictions when training a machine learning model on this data.
Unsampling: This approach of upsampling the minority class aims to balance the class distribution and provide equal representation of both classes during the model training process. By having a balanced dataset, the machine learning model can learn from all classes effectively and produce more accurate and unbiased predictions.
the code snippet currently updates the 'train_df' DataFrame with the upsampled data. It's important to consider how this impacts the overall data handling and model training process, such as whether further splitting of the dataset into training and validation sets is needed and whether additional preprocessing steps are required.
# Data Scaling :
This scaling process ensures that the variables are on a similar scale, which can be beneficial for various machine learning algorithms that are sensitive to the magnitude of variables.
the 'train_df' DataFrame exists, and the specified columns ('Temperature(°C)', 'Wind speed (m/s)', 'Humidity(%)') are present. Additionally, it's important to ensure that the scaling is performed consistently across the training, validation, and test sets, if applicable, to avoid data leakage and maintain consistency in the scaling process.
# Dimesionality Reduction: 
It does not require dimensionality reduction, you can proceed without applying such techniques. 
# Data Splitting :
Splitting the data into training and testing sets is an important step in machine learning. The training set is used to train the model, while the testing set is used to evaluate the model's performance on unseen data. The choice of the splitting ratio depends on various factors, such as the size of the dataset and the specific requirements of the analysis. In this case, a test_size of 0.2 indicates an 80:20 split, which is a commonly used ratio. Adjusting the test_size value allows you to control the trade-off between the size of the training set and the size of the testing set.
Handling Imbalanced Dataset :
# ML Model - 1---RandomForestRegressor
Basically, this code provides a basic implementation of a Random Forest regression model for prediction and evaluation. You can further enhance the model by tuning hyperparameters, performing cross-validation, and exploring other evaluation metrics based on your specific needs and the characteristics of the dataset.
 A Random Forest Regressor object is created with 100 estimators (decision trees) using the `RandomForestRegressor` class from `sklearn.ensemble`.
- The model is trained on the training data using the `fit` method.
- Predictions are made on the testing data using the `predict` method.
- Mean squared error (MSE) and R-squared are calculated to evaluate the model's performance using the `mean_squared_error` and `r2_score` functions from `sklearn.metrics`.
- The MSE and R-squared values are printed to assess the model's performance.
 R-square value is 0.9801.
This suggests that the model is a good fit for the data and is performing well in predicting the number of bikes rented during a given hour.
# ML Model - 2: XGBRegressor

- XGBRegressor is a machine learning model based on the gradient boosting algorithm using the XGBoost library.
- Similar to the Random Forest Regressor, the dataset is split into training and testing sets.
- An XGBRegressor object is created with 100 estimators using the `XGBRegressor` class from `xgboost`.
- The model is trained on the training data.
- Predictions are made on the testing data.
- MSE and R-squared are calculated to evaluate the model's performance.
- The evaluation metrics are plotted using a bar chart.

# ML Model - 3: GradientBoostingRegressor

- GradientBoostingRegressor is another machine learning model based on the gradient boosting algorithm from the `sklearn.ensemble` module.
- The dataset is split into training and testing sets.
- A GradientBoostingRegressor object is created with 100 estimators and a learning rate of 0.1.
- The model is trained on the training data.
- Predictions are made on the testing data.
- MSE, mean absolute error (MAE), and R-squared are calculated to evaluate the model's performance.
- The evaluation metrics are printed and plotted using a bar chart.



For all three models, the evaluation metrics provide an indication of how well the models perform. Lower values of MSE and MAE indicate better predictive accuracy, while a higher R-squared value (closer to 1) indicates a better fit of the model to the data. The bar charts visualize the evaluation metric scores for easy comparison between the models.

# Conclusion : 
The combination of the dataset, machine learning techniques, and analysis provides valuable insights into the factors driving bike rental demand and demonstrates the power of machine learning in understanding and predicting complex phenomena.



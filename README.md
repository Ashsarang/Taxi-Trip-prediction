# Taxi-Trip-prediction
**Problem Statement**

With over 7 billion people inhabiting the Earth, transportation has become a vital necessity alongside food, water, and shelter. The rapid technological advancements witnessed over the last two decades have ushered in a more efficient mode of transportation through internet and app-based transport systems. New York City stands as a prime example of such technological advancement, boasting an extensive network of subways, buses, and taxi services. With over 10,000 taxis operating in the city and nearly 50% of the population lacking personal vehicles, taxis have become the primary mode of transportation for many New Yorkers. Consequently, the city witnesses over 100 million taxi trips annually.

The primary objective at hand is to develop a predictive model capable of accurately estimating taxi trip durations. Such a model would facilitate the efficient matching of the right cabs with the right customers, streamlining the transportation process for both passengers and drivers alike.

**Data Overview**

The dataset utilized for this project originates from the 2016 NYC Yellow Cab trip record data, which was accessed through Big Query on the Google Cloud Platform. Originally published by the NYC Taxi and Limousine Commission (TLC), the dataset has been sampled and cleaned specifically for this project's objectives. Utilizing various attributes associated with individual trips, the goal is to predict the duration of each trip within the test set.

**Data fields**:

id - a unique identifier for each trip

vendor_id - a code indicating the provider associated with the trip record

pickup_datetime - date and time when the meter was engaged

dropoff_datetime - date and time when the meter was disengaged

passenger_count - the number of passengers in the vehicle (driver entered value)

pickup_longitude - the longitude where the meter was engaged

pickup_latitude - the latitude where the meter was engaged

dropoff_longitude - the longitude where the meter was disengaged

dropoff_latitude - the latitude where the meter was disengaged

store_and_fwd_flag - This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server - Y=store and forward; N=not a store and forward trip

trip_duration - duration of the trip in seconds


**Approach**

The following steps were followed in the project:

Data Preprocessing and cleaning: Done data preprocessing by converting some columns' datatypes , by adding some new columns and removimng outliers

Exploratory Data Analysis: Did Exploratory Analysis which includes Univariate as well as Bivariate Analysis.

Data Split: The preprocessed data was split into training and test sets on a random state of 0. By using training data we trained our predictive model and we used testing data to evaluate our prediction.

Model Training: The models were trained using the training data, and these models are optimized by some Hyperparameter settings.

Model Evaluation: The performance of the trained models was evaluated using metrics such as mean absolute error, root mean squared error, and R-squared. The model that performed the best on the test data was selected.

Model Deployment: The selected model was deployed in a live production setting, where it could make real-time predictions of bike demand. The model's performance was monitored over time to ensure its accuracy and usefulness.

**Models Used**

Models Used For modeling we tried various regression models such as

1)Linear Regression

2)Random Forest

3)XG Boosting

All these models were fine tuned using a random search method with repeated cross-validation (CV) to ﬁnd the best hyperparameters. We also found out Feature importance so that we get to know about the features which are highly important.

**Result**

We got the best model accuracy in Xgboost model,r2 score of 0.83 in test data..The RMSE score of Xgboost model is 0.28

**Output**

![285177003-085a8fc0-0a3b-4eab-89ab-7efe121ed844](https://github.com/Ashsarang/Taxi-Trip-prediction/assets/138696559/ee1a95f5-17f8-4790-8b2b-675206e96d90)




**Conclusion**

During our analysis, we began by preprocessing the data, which involved creating additional columns and cleaning the dataset by removing outliers. Subsequently, we conducted exploratory data analysis (EDA) on all the features in our dataset. This involved both univariate and bivariate analyses on these variables. We studied the numerical variables, calculated their correlations, and examined their relationships with the dependent variable. To address multicollinearity, we utilized Variance Inflation Factor (VIF) analysis. Additionally, we applied One-Hot Encoding by adding dummy columns to handle categorical variables.

We employed three machine learning algorithms: Linear Regression, Random Forest, and XG Boosting. To optimize the performance of our models, we performed hyperparameter tuning. This iterative process aims to fine-tune the parameters of the algorithms to achieve better predictive accuracy and generalization on unseen data.

Some Facts:

Our base model, Linear Regression, achieved an R2 score of 0.65 on the test data, serving as our reference for model comparison.

The best-performing model was XGBoost, yielding an impressive R2 score of 0.83 on the test data, with an RMSE score of 0.28.

Following closely, the RandomForest Regressor attained an R2 score of 0.72 on the test data, with an RMSE score of 0.36. Notably, without proper hyperparameter tuning, RandomForest tends to exhibit overfitting issues and extended runtime, as observed practically.

Examining the data, we notice a surge in both trip duration and the number of rides during the evening hours, indicating a natural pattern likely attributed to traffic congestion.

Furthermore, there's a notable increase in pickup numbers during the 4-6 pm window, possibly due to the conclusion of office hours.

March emerges as the month with the highest taxi ride frequency, possibly owing to salary disbursements toward month-end or vacation periods.

Conversely, taxi trips are at their lowest on Mondays and comparatively lower on Sundays, suggesting a preference for staying indoors rather than navigating through traffic, particularly on Sundays.

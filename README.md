# Appliances-Energy-Prediction
--- 
## Problem Statement:
---
#### This project deals with predicting appliances energy consumption of a particular household in Belgium based on the temperature and humidity levels of different rooms in the building and the weather reports in the area over a period of 4.5 months.

#### The data set is at 10 min for about 4.5 months. The house temperature and humidity conditions were monitored with a ZigBee wireless sensor network. Each wireless node transmitted the temperature and humidity conditions around 3.3 min. Then, the wireless data was averaged for 10 minutes periods. The energy data was logged every 10 minutes with m-bus energy meters. Weather from the nearest airport weather station (Chievres Airport, Belgium) was downloaded from a public data set from Reliable Prognosis (rp5.ru) and merged together with the experimental data sets using the date and time column. Two random variables have been included in the data set for testing the regression models and to filter out non-predictive attributes (parameters).
---

## Dataset Link
---
- http://archive.ics.uci.edu/ml/datasets/Appliances+energy+prediction
## Dataset Information
- Number of instances: 19,735
- Number of attributes: 29


## Objective of Project:
--- 

####  The increasing trend in energy consumption is becoming cause of concern for the entire world, as the energy consumption is increasing year after year so is the carbon and greenhouse gas emission, the majority portion of the electricity generated is consumed by industrial sector but a considerable amount is also consumed by residential sector. 

#### It is important to study the energy consuming behaviour in the residential sector and predict the energy consumption by home appliances as it consume maximum amount of energy in the residence. This project focuses on predicting the energy consumption of home appliances based on humidity and temperature.

---
# Introduction  
### This project aims to predict the energy consumption of home appliances. With the advent of smart homes and the rising need for energy management, existing smart home systems can benefit from accurate prediction. If the energy usage can be predicted for every possible state of appliances, then device control can be optimized for energy savings as well. This is a case of Regression analysis which is part of the Supervised Learning problem. Appliance energy usage is the target variable while sensor data and weather data are the features. 
 
# Steps involved: 
### Exploratory Data Analysis: 
### ● Data Pre-processing:
#### Cleaning is the process of removing undesired features, values, or any suffix, prefix, or anything which can produce an exception. 
#### Transforming is completely a different process, transforming is required to ensure the consistent data type of features because inconsistent data type will generate an obstacle during the execution of the program. 

#### ● Scaling and Normalization operations on data and splitting the data into training, validation, and testing sets.

### ● Unwanted Data Removal
#### we ensured to make data type of feature consistent by removing the unwanted structure from the values of features, to make them usable.

### ●  Null values Treatment:
#### Our dataset contains no null values, so, there is no need for an explicit null value treatment


### ●  Data Visualization:  
#### Visual representation of data to find the degree of correlations between predictors and target variables and find correlated predictors. Additionally, we can see ranges and visible patterns of the predictors and target variables. 


### ●	Encoding of categorical columns 
#### We used One Hot Encoding to produce binary integers of 0 and 1 to encode our categorical features because categorical features that are in string format cannot be understood by the machine and needs to be converted to the numerical format.

### ●	Feature Engineering: 
#### Finding relevant features, engineer new features using methods like PCA if feasible.
### •	Standardization 
#### Our main motive through this step was to scale our data into a uniform format that would allow us to utilize 


#### The data in a better way while performing fitting and applying different algorithms to it. 

#### The basic goal was to enforce a level of consistency or uniformity to certain practices or operations within the selected environment.

### •	Model Selection:  
#### Experiment with various candidate algorithms to find out the best algorithm for this use case.

### •	Model Tuning:  
#### Fine-tune the selected algorithm using hyperparameter tuning to increase performance without overfitting.

### •	Testing:  
#### Evaluate the model on the testing dataset.
 ![Screenshot (161)](https://user-images.githubusercontent.com/75175373/150628344-c4fb6bfa-024e-4525-947f-b06c1339649c.png)

   ### Fig: Project Outline




### 3. Descriptive Statistical Analysis: 
#### Descriptive statistics are brief descriptive coefficients that summarize a given data set, Descriptive statistics are broken down into measures of central tendency and measures of variability (spread). Measures of central tendency include the mean, median, and mode, while measures of variability include standard deviation, variance, minimum and maximum variables.

### 3.1 Observations (Temp Feature) 

![Screenshot (129)](https://user-images.githubusercontent.com/75175373/150628425-b30d1f2a-7db7-4c56-8a11-3f4477448056.png)
### Fig: Descriptive Statistics (Temperature Dataframe)
1.	The average outside temperature over a period of 4.5 months is around 7.5 degrees. It ranges from -6 - 28 degrees. 

2.	While the average temperature inside the building has been around 20 degrees for all the rooms. It ranges from 14 - 30 degrees. 

3.	This implies Warming appliances have been used to keep the insides of the building warm. There must be some sort of direct correlation between temperature and consumption of energy inside the house. 


### 3.2 Observations (Humidity Features)
![Screenshot (128)](https://user-images.githubusercontent.com/75175373/150628430-a32c68fe-369d-450e-b5a1-b3857fd8e0c4.png)
### Fig: Descriptive Statistics (Humidity Features)

1.	Average humidity outside the building has been higher than the average humidity inside.

2.	Average humidity at the weather station is significantly higher compared to outside humidity near the building. 

3.	Average humidity in the bathroom is significantly higher compared to other rooms due to obvious reasons. 

### Heatmap Corelation Between Features:
![Screenshot (138)](https://user-images.githubusercontent.com/75175373/150628493-e02851f9-958a-4c6b-9df3-4a619d08f198.png)
### Fig: Heatmap Correaltion Between Features
### 3.3 Observations from Heatmap correlation plot:
#### a.	Features related to temperature Almost all the temperature measures in different rooms are highly linearly correlated with each other. However, there is little to no correlation between temperature features and target variables.
#### b.	Features related to humidity Almost all the humidity measures in different rooms are highly linearly correlated with each other. However, there is little to no correlation between humidity features and target variables. 
### c.	Weather data 
#### Dewpoint shows a higher correlation with most of the temperature and humidity level features than any other weather parameters. However, its correlation with the target variable is low. Pressure, wind speed, and visibility show little correlation with temperature and humidity features as well as the target variable. 

### Target Variable Distribution:
![Screenshot (140)](https://user-images.githubusercontent.com/75175373/150628530-eb515309-a4e2-4fa3-ba03-277b26f7c652.png)
### Fig: Target Variable Distribution

#### In the given data set the target variable is Appliances which denote the energy consumption by appliances in w/h. The target variable was rightly skewed so we have performed different transformations on it, log transformation has given a better result than any other transformation.
### Observations  
#### •	Energy consumption of appliances ranges from 10 Wh to 1080 Wh.
#### •	About 75 % of energy values lie below 100 Wh, and about 93 % of them lie below 300 Wh. 
#### •	Our target variable seems to be highly skewed, and our task is to predict the usual as well as the large surges in energy in the building.
---

### Model Performance:
### The model can be evaluated by various metrics such as:
#### 1. Root Mean Squared Error (RMSE)
#### The term root means square error (RMSE) is the square root of mean squared error (MSE). RMSE measures the differences between values predicted by a hypothetical model and the observed values. In other words, it measures the quality of the fit between the actual data and the predicted model. RMSE is one of the most frequently used measures of the goodness of fit of generalized regression.
![image](https://user-images.githubusercontent.com/75175373/150628675-bf1a4f81-0d25-401b-aa6b-f528910bb491.png)
### Fig: RMSE
#### R2 Square:
#### The coefficient of determination also called as R2 score is used to evaluate the performance of a linear regression model. It is the amount of variation in the output. The dependent attribute is predictable from the input independent variable(s). It is used to check how well-observed results are reproduced by the model, depending on the ratio of total deviation of results described by the model.


![image](https://user-images.githubusercontent.com/75175373/150628667-f398ddca-5a3a-4d19-b908-cad8cc12f413.png)
### Fig: R2 Square
### Results:
![image](https://user-images.githubusercontent.com/75175373/150628715-0e723bbb-23ab-415d-a4d0-de064def2564.png)
### Fig: Model Result Trained With PCA Features
![image](https://user-images.githubusercontent.com/75175373/150628731-8e71af75-074f-46f9-8cdf-1994e628e19a.png)


![image](https://user-images.githubusercontent.com/75175373/150628735-9f3d922a-4a57-494d-818a-30206bd624b6.png)

### Fig: Model Result Trained without PCA Features


![image](https://user-images.githubusercontent.com/75175373/150628737-a43e14ef-63f1-4dfa-8b25-fec12711db25.png)


## Feature Importances:
![image](https://user-images.githubusercontent.com/75175373/150628782-cdd4ea00-9b17-4d3e-9369-4e280daf6617.png)

### Fig: Feature Importances With PCA Features


![image](https://user-images.githubusercontent.com/75175373/150628805-b9add121-ce7f-4ffb-9d3a-f439b2005bd2.png)

### Fig: Feature Importances Without PCA Features

# Conclusion:
--- 
### 1.	The humidity and temperature feature has little to no linear correlation with the target variable.
### 2.	The time zone of the day plays an important role in deciding the power consumption of appliances.

### 3.	The best Algorithm to use for this dataset is Extra Trees Regressor (tree-based algorithm).
### 4.	PCA helped us to reduce our feature set dimension considerably without affecting the performance of our models significantly.
### 5.	The untuned model was able to explain 75.50% of the variance (R2 score = 0.7550) on the test set, while the tuned model was able to explain 75.84% of the variance (R2 score = 0.7584).
### 6.	The least RMSE score on the test data set is found to be around 0.5 by the Extra trees regressor model, which is considered good compared to other models.

### 7.	Tree-based models are by far the best model while dealing with a data set that has most of its features have

### 8.	no linear correlation with the target variable. For similar reasons, linear 

### 9.	models such as linear regression, Ridge, and Lasso perform the worst.

---




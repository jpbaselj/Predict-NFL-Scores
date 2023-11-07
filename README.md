# Predict-NFL-Scores
Springboard Data Science course capstone 1 project


NFL Betting Outcome Prediction
Author: John (JP) Baselj

Table of Contents
1. Introduction
2. Problem
3. Data
4. Data Acquisition, Processing, and Analysis
5. Data Preparation for Modeling
6. Modeling Approach
7. Modeling Results
8. Conclusion


### Introduction
This GitHub repository contains the code and documentation for a data science project aimed at predicting NFL betting outcomes. The project utilizes data available through Kaggle and Pro Football Reference to create a predictive model for how NFL teams will perform against the betting spread in a given game. The ultimate goal is to apply this model to future NFL games to potentially inform betting strategies.

### Problem
The problem addressed in this project is predicting the performance of NFL teams against the betting spread in a given game. Key factors considered in this analysis include teams' scoring history, game location, weather conditions, and more. The project aims to provide insights that can be used for betting on NFL games.

### Data
The primary dataset used in this project is "spreadspoke_scores.csv" from Kaggle, containing records of NFL games from 1966 to 2022. Additionally, the "nfl_teams.csv" dataset from Kaggle was used to identify NFL franchises and simplify the data for modeling purposes. Weather data was partially missing, and games with missing weather information were assumed to have neutral weather conditions.

### Data Acquisition, Processing, and Analysis
The raw dataset consisted of 13,516 entries, but only 11,027 entries with complete betting data were used, focusing on predicting performance against the spreads. Various data preprocessing steps were applied, including the handling of incomplete weather data and encoding categorical variables. The distribution of home team performances against the spread was analyzed, and no significant trends in mean and standard deviation over time were observed.

### Data Preparation for Modeling
To prepare the data for modeling, fields dependent on game results were removed. Categorical variables were encoded, and numeric data was scaled using StandardScaler from scikit-learn. A validation set for the 2022 NFL season was set aside for evaluating the trained models.

### Modeling Approach
Due to the nature of the data, a modified time series approach was used to train and evaluate the models. TimeSeriesSplit from scikit-learn was employed to create train/test splits. Two modeling approaches were explored:

Discrete variable - Will the home team beat the spread?
Logistic Regression Model
Random Forest Classifier Model
Continuous variable - By how many points will the home team beat or lose to the betting spread?
Random Forest Regressor Model
Linear Regressor Model

### Modeling Results
The models were evaluated based on accuracy, with the following results:

Random Forest Classifier Accuracy: 0.551
Random Forest Regressor Accuracy: 0.544
Logistic Regression Model Accuracy: 0.523
Linear Regressor Accuracy: 0.511
The Random Forest Classifier was selected for further exploration. Attempting to place bets on the top 50% of game predictions did not significantly improve accuracy. The model was applied to the 2022 NFL season and achieved an accuracy of 51%, suggesting potential overfitting in the training data.

### Conclusion
The validation testing results indicate that the best model built from the dataset is likely not suitable for predicting NFL games and generating a profit. Predicting home team performance against the betting spread is a complex task, influenced by various factors beyond the dataset's scope. Future attempts could consider more sophisticated data, such as injury information, key personnel attributes, and team playstyle changes. Exploring advanced machine learning techniques, like neural networks, may also be valuable.
# NFL Betting Outcome Prediction
Springboard Data Science Course Capstone Project

Author: John (JP) Baselj
![NFL Team Logos](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/documentation/nfl-logos.jpeg)

## Introduction
This GitHub repository contains the code and documentation for a data science project aimed at predicting NFL betting outcomes. The project utilizes data available through Kaggle and Pro Football Reference at [Kaggle Scores](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=spreadspoke_scores.csv) to create a predictive model for how NFL teams will perform against the betting spread in a given game. Key factors considered in this analysis include teams' scoring history, game location, weather conditions, and more.

## Technologies and Tools
- Python
- Pandas
- Scikit-Learn
- Matplotlib and Seaborn
- Jupyter Notebook
- PCA
- SimpleImputer
- TimeSeriesSplit
  
## Data
The primary dataset, [spreadspoke_scores.csv](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=spreadspoke_scores.csv), covers NFL game records from 1966 to 2022. To streamline data representation, the [nfl_teams.csv](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=nfl_teams.csv) dataset was used to identify NFL franchises. 

## Data Wrangling
[Data Wrangling Notebook](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/Cap2_1_data_wrangling.ipynb)
Weather data was partially missing, with games lacking weather information assumed to have neutral conditions. The dataset, initially comprising 13,516 entries, was reduced to 11,027 entries with complete betting data. Various preprocessing steps were applied, including handling incomplete data fields and encoding categorical variables. 

## Data Preparation
[EDA Notebook](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/Cap2_2_EDA.ipynb)
[Preprocessing Notebook](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/Cap2_3_preprocessing_and_data_development.ipynb)
To prepare the data for modeling, fields dependent on game results were removed, and numeric data was scaled using StandardScaler from scikit-learn. A validation set for the 2022 NFL season was set aside for evaluating the trained models.

## Modeling 
[Modeling Notebook](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/Cap2_4_Modeling.ipynb)
Due to the nature of the data, a modified time series approach was used to train and evaluate the models. TimeSeriesSplit from scikit-learn was employed to create train/test splits. Two modeling approaches were explored, and the following model types were evaluated for each:

##### Target as a Discrete variable - "Will the home team beat the spread?"
- Logistic Regression Model
- Random Forest Classifier Model
##### Target as a Continuous variable - "By how many points will the home team beat or lose to the betting spread?"
- Random Forest Regressor Model
- Linear Regressor Model

### Modeling Results
The preliminary models were evaluated based on accuracy, with the following results:

* Random Forest Classifier Accuracy: 0.551
* Random Forest Regressor Accuracy: 0.544
* Logistic Regression Model Accuracy: 0.523
* Linear Regressor Accuracy: 0.511
  
The Random Forest Classifier was selected for further hyperparameter tuning and evaluation. Attempting to place bets on the top 50% most confident game predictions did not significantly improve accuracy. The model was applied to predict the valiation set of games from 2022 NFL season and achieved an accuracy of 51%, suggesting potential overfitting in the training data.

## Conclusion
The validation testing results indicate that the best model built from the dataset is likely not suitable for predicting NFL games and generating a profit. Predicting home team performance against the betting spread is a complex task, influenced by various factors beyond the dataset's scope. Future attempts could consider more sophisticated data, such as injury information, key personnel attributes, and team playstyle changes. Exploring advanced machine learning techniques, like neural networks, may also be valuable.

## Project Report
[Final Report PDF](https://github.com/jpbaselj/Predict-NFL-Scores/blob/main/Reports/Cap2_Final_Report.pdf)

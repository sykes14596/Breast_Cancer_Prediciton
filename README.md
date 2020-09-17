# Predicting the Presence of Breast Cancer

The goal of this project was to develop a model that would accurately predict the presence of breast cancer within a patient. On a personal development level, the aim of this project was to practice the skill known as feature selection, as well as continue to use and develop data analysis skills learned via completion of Jose Portilla's "Python for Data Science Bootcamp" course on [Udemy](https://www.udemy.com/course/python-for-data-science-and-machine-learning-bootcamp/learn/lecture/17739846?start=0).

Two different types of model were implemented and both managed to acheive an F1-score of 99%, as well as 99% accuracy on the test set. 

## Table of Contents

* [Technologies](#technologies)
* [Exploratory Data Analysis](#exploratory_data_analysis)
* [Feature Selection & Model Building](#feature_selection_&_model_building)
* [Model Performance](#model_performance)

## Technologies

* Python: 3.7.7
* Numpy: 1.19.1
* Pandas: 1.1.0
* Seaborn: 0.10.1
* Scikit-Learn: 0.23.1
* Matplotlib: 3.2.2
* Imbalanced-Learn: 0.7.0

## Exploratory Data Analysis

I investigated the effect that each variable had on the presence of breast cancer through the use of boxplots. The relationships between the independent variables were analysed and a significant relationship was highlighted. Analysis showed that each variable had at least some influence on the presence of breast cancer. I looked at countplots for the dependent variable and noticed a slight imbalance. Highlights from the EDA are shown below.

![alt text](https://github.com/sykes14596/Breast_Cancer_Prediciton/blob/master/Images/correlation_matrix.png "Correlation Matrix")
![alt text](https://github.com/sykes14596/Breast_Cancer_Prediciton/blob/master/Images/rad_area_per_pairplot.png "pairplot")
![alt text](https://github.com/sykes14596/Breast_Cancer_Prediciton/blob/master/Images/diagnosis_countplot.png "Countplot")

## Feature Selection & Model Building

Determining the optimal number of features for use within our models proved difficult. Feature importances were generated and models were created using Random Forest Classifiers and XGBoost Classifiers with varying numbers of the most important features, along with the use of GridSearch,  to find the model which produced the highest F1-score. The F1-score metric was used for analysis since it considers both false positives and false negatives, as well as recall and precision values. 

Using the Random Forest Classifier, the effect of using the SMOTE technique to balance the target class was investigated. It became apparent that models achieved increased F1-scores after applying SMOTE. 

![alt text](https://github.com/sykes14596/Breast_Cancer_Prediciton/blob/master/Images/RFC_SMOTE_plot.png "SMOTE Plot")

Final models were created based on the F1-scores achieved in the feature selection process. 

## Model Performance

Both models were able to correctly classify all but one of the test cases, resulting in 99% accuracy. Full results are shown below.

* Random Forest Classifier using most important 18 variables: F1-Score = 0.99, Accuracy = 99%
* XGBoost Classifier using most important 26 variables: F1-Score = 0.99, Accuracy = 99%.
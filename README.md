# Breast Cancer: Machine Learning Model

## Overview

I trained a machine learning model on a public diagnostic breast cancer dataset. The goal of the model is to predict whether a given digitized image of a breast mass contains benign or malignant cells. The model was used to help answer the following research question:

#### <i>Which characteristics of a breast cell nucleus are the most predictive of a malignant cell?</i>

## Dataset 

The dataset is a public Kaggle dataset concerning diagnostic breast cancer data from 1995. Digitized images of breast masses were collected to analyze features such as the average radius of cell nuclei, the average number of concave portions on the contour, and so on. Each image is either classified as benign (i.e. non-cancerous) or malignant (i.e. cancerous).

The dataset is included as a CSV file in this repository and can also be found at https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

The dataset is also hosted at UC Irvine's machine learning repository at https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic

![Feature Distributions for Diagnoses](https://github.com/cwentz12/Breast-Cancer-Machine-Learning-Model/assets/115527862/2ce88529-5940-44f9-84b5-514049f08805)

## Insights

* After exploratory data analysis, I decided to proceed with an XGBoost machine learning model. The data was split into 80/20 training/testing subsets. I chose to evaluate my model's performance with the F1 score.

![confusion matrix](https://github.com/cwentz12/Breast-Cancer-Machine-Learning-Model/assets/115527862/57742578-a0e9-4793-b989-8b92f5a6873c)



* The XGBoost model received a 93.02% F1 score, which was an impressive initial result. The F1 score is the harmonic mean between the precision score and the recall score.

* Out of 114 images in the testing dataset, the model only had 6 incorrect diagnosis predictions.

The model identified the the top 4 most predictive features as:
1) The mean of the 3 largest concave points in images
2) The mean of the 3 largest nuclei areas in images
3) The standard deviation in gray-scale values of the nuclei
4) The standard error of nuclei areas in images




## Recommendations

The insights can assist us in attempting to build models with even higher performance:

1) We can use the identified features to exclude less relevant features from model training
2) We can also experiment with combining features in some way
3) We could experiment with other types of models like a Random Forest model and compare results to select a champion model

The insights can also be used:
* For further breast cancer research
* To help spot early warning signs of malignant cells in patients
* To help in the development of breast cancer treatment options

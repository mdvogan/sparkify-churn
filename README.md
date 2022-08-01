# sparkify-churn
Udacity Nanodegree Capstone Project

This repository is for the capstone project of the Udacity Data Science nanodegree.
The goal of the project is to use the PySpark API to build a music streaming
churn rate model that could be deployed in the cloud

## Blog post
https://medium.com/@vogan.michael/predicting-music-streaming-churn-with-spark-d3db0176fce5


##Libraries used
* pyspark
* datetime
* numpy
* pandas
* matplotlib

##Datasets used
* mini_sparkify_event_data.json

The Jupyter notebook is divided into four sections

## Section 1 - Load and Clean Dataset
This section loads the user log sample data and cleans data.

Note 1: Only cleaning step needed was to remove blank userIDs for unregistered
users on the site

## Section 2 - Exploratory Data Analysis
The code in this section defines the target variable and features, as well
as performs analysis of how they relate.

Note 1:  the data is highly imbalanced with only 52 of 278,154 records
being a churn event, which creates difficulties for model evaluation later on.

Note 2: there is one record where the time since registration is negative one day.
I replaced this value with one to be consistent with the other records

## Section 3 - Feature Engineering
This section is creates the feature vectors and dataset used to fit the model
in the next section

## Section 4 - Data Modeling
The code in this section trains and tests an optimized logistic regression using
k-fold cross validation to find the best elastic net parameter to prevent
overfitting.

Note 1: the model does not appear to predict any churn events when applied to
either the training or testing datasets. This gives misleading results because
of the imbalanced data, which the F1 score is supposed to address.

## Acknowledgements
Udacity for providing the course and assignment review
as well as the Sparkify data

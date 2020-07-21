# Starbucks Capstone Challenge
You can read my Medium Blog Post [here](https://medium.com/@c.kuan/starbucks-capstone-challenge-for-udacity-data-science-nanodegree-469d0762547c): 
### Introduction

This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

## Problem Statement
In this capstone project I aim to build machine learning models to predice if one is going response (view or complete) to the offer. To acheive that, the following approaches will be conducted:
- data preprocessing and cleaning
- exploratory data analysis (EDA)
- build machine learning models and evaluate the performence

### Requirements
Python 3.5+  
NumPy  
Pandas  
Seaborn
Matplotlib
Sklearn
 
### Data Sets

The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

**portfolio.json**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Metrics
Accuracy will be used to evaluated the models because this a simple classification problem, either: offer viewed and offer completed.


## Summary
1. Female customers spend more than male and other
2. Female customers complete more offers than male
3. There are a group of people do not provide gender/age/income information   
    3.1 This gropu of people spend a lot less than other customer   
    3.2 They do not tend to complete offer
4. When the channels include social media, the offer viewed rate are signigicantly higher (0.5 to 0.9)
5. With longer offer duration, the offer completed rate seem to be higher
6. Random forest model is able to predict wether customer views the offer with 81% accuracy
    6.1 The most important feature for viewing the offer is wether the offer is from social media channels  
    6.2 Income, when to become member and age are also important
7. Random forest model is able to predict wether customer completes the offer with 78.8% accuracy
    7.1 The most important feature for completing the offer is wether the income of the customer  
    7.2 The age and when to become member, reward, difficulty and duration of the offer also impact the offer completion
##  Table of Contents
1. [Installation](#Installation)
2. [Description](#Description)
3. [Data](#Data)
4. [File Descriptions](#File-Descriptions)
5. [Results](#Results)

## Installation
- Python 3.7.2
- Libraries: 
  - [NumPy](http://www.numpy.org/)
  - [Pandas](http://pandas.pydata.org)
  - [matplotlib](http://matplotlib.org/)
  - [seaborn](https://seaborn.pydata.org/)
  - [scikit-learn](http://scikit-learn.org/stable/)

You will also need to have software installed to run and execute an [iPython Notebook](http://ipython.org/notebook.html)

## Description
Credit risk management remains a significant challenge for banks given the inefficient data management, limited view of risk measures, lack of risk assessment tools, and less than intuitive visualization process into the borrowers’ ability to pay back. A thorough assessment of the borrowers’ capability and complete understanding of loan loss reserve is crucial to managing credit risk exposure and mitigating losses. In this scenario, traditional scorecards by themselves are no longer enough to determine credit lending.
This project compares the performances of few algorithms to determine the credit worthiness of customers. The dataset that has been used in this project contains information on default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients in Taiwan from April 2005 to September 2005. The 3 machine learning algorithms used in this project are Logistic Regression, Decision Tree Classification, and Random Forest Classification. For comparison of the performances of these models, ROC Curve and Cross Validation Accuracy has been used.

## Data 
`default of credit card clients.xls` - This dataset contains information on default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients in Taiwan from April 2005 to September 2005.
Dataset Source : [Taiwan Bank Dataset](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)


## File Descriptions

You can find the results of the analysis in the following iPython Notebook Notebook:
* [Credit_Worthiness_of_customer.ipynb](https://github.com/pranjal0207/credit-worthiness-of-customer/blob/master/Credit_Worthiness_of_customer.ipynb)

Alterinatively, run one the following commands in a terminal after navigating to the top-level project directory `predicting_creditworthiness/` (that contains this README):

```bash
ipython notebook Credit_Worthiness_of_customer.ipynb.ipynb
```  
or
```bash
jupyter notebook Credit_Worthiness_of_customer.ipynb.ipynb
```

This will open the iPython Notebook software and project file in your browser.

## Results

To identify the creditworthy applicants, we performed the following steps:

  **Step 1: Preprocessing**
  - Removed certain collumns either due to low variability or no logical connection with the target.
  - Cleaned data of ambiguous data values in some rows.
  - Split the data into training and testing sets with `train_test_split()` 
  
  **Step 2: Data Visualization**
  - Calculating the target (Default) percentage (Yes, No).
  - Describing the data for mean, median, etc for all individual collumns.
  - Graphically Representing the dependency of various collumns on target (Default).

  **Step 3: Creating a Training and Predicting Pipeline**
  - Initialized and fit classification models:
    - `LogisticRegression()`
    - `DecisionTreeClassifier()`
    - `RandomForestClassifier()`
  - Implemented `LogisticRegression()` on Original Data, Standardized Data and Data obtained post Recursive Feature Elimination and obtained a confusion matrix for along with the respective accuracy
  - Implemented `DecisionTreeClassifier()` on standardized data and obtained a confusion matrix along with the accuracy.  
  - Implemented `RandomForestClassifier()` on standardized data and improved the result by employing Hyperparameterization via `RandomSearchCV()` for the following parameters `n_estimators`, `max_features` and `max_depth` and obtained a confusion matrix along with the accuracy.
  
  **Step 4: Comparison of Model Performance**
  - Plotted a Receiver operating characteristic (ROC) Curve to predict which model is better distinguishing between positive and negative class  
  - K-fold Cross Validation was implemented to check which model provided the least bias and avoided overfitting of data


# Project-Bondora-Financial-risk-modelling-of-European-P2P-lending-platform


## Table of content

1. [Problem Statment](#Problem-Statment)
2. [Exploratory data analysis](#Exploratory-data-analysis)
3. [Features engineering](#Features-engineering)
4. [Modeling](#Modeling)
5. [Model Pipeline](#Model-Pipeline)

The main purposes of this analysis are to summarize the characteristics of variables that can affect the loan status and to get some ideas about the relationships among variables.




## Problem Statment

## Exploratory data analysis

## Features engineering

FreeCash

PrincipalWriteoffs <br>

PrincipalDebtServicingCost <br>

InterestAndPenaltyWriteOffs<br>

InterestAndPenaltyDebtServicingCost <br>
BidPrinciple<br>

PurchasePrice<br>

IncomeTotal<br>

LoanDuration<br>

"Amount"


To create the three target variables for feature engineering, we will follow the provided formula for calculating EMI, and use the borrower's assets and liabilities to calculate their eligible loan amount.

### EMI

EMI: We will use the formula EMI = P * r * (1+r)^n/((1+r)^n-1), where P is the loan amount, r is the monthly interest rate, and n is the loan tenure in months. We will use the provided data for loan amount, interest rate, and loan duration to calculate the EMI for each borrower.

### Eligible Loan Amount (ELA)

Eligible Loan Amount (ELA): We will calculate the ELA using the borrower's assets and liabilities. 
The formula is ELA = Assets - Liabilities, where assets represent the borrower's income and liabilities represent their total debts. We will use the provided data on borrower income and total liabilities to calculate ELA. If the ELA is less than 30% of the borrower's total income minus their total liabilities, we will only allow the ELA calculated from the formula. Otherwise, we will allow the borrower to borrow only the amount calculated from the 30% threshold calculation.


### Rate Of Interest

Preferred ROI: We will calculate the ROI based on the amount borrowed and the interest rate. The formula for ROI is ROI = investment gain / investment base.
We will use the amount borrowed and the interest rate to calculate the ROI for each loan. We were not provided with enough information on how to determine the borrower's preferred ROI, so we will use the calculated ROI as a proxy


### Employee Status

### Use of loan

### Gender

### Percentage of risk 

We have developed a reliable algorithm for calculating the financial risk of borrowers. This calculation involves using a formula that takes into account the borrower's salary and liabilities, particularly the percentage of their income dedicated to paying off existing debts.
To create the target variable, we focus on the borrower's remaining salary after deducting all their liabilities. From this remaining salary, we then factor in the borrower's monthly loan payments (EMI) to determine their monthly savings. This savings amount serves as the basis for assessing the borrower's financial risk.
Our approach involves assigning a risk score based on the borrower's savings relative to their EMI. For example, if a borrower has a savings amount that exceeds 50% of their EMI, their risk score will be low. Conversely, if their savings amount is less than 20% of their EMI, their risk score will be high. By using this system, we can provide a reliable and accurate financial risk assessment for borrowers.



## Modeling


This project is a collaboration between our team that worked on developing a machine learning model using Gradient Boosting and VSM (Vector Space Model). We aimed to achieve the highest accuracy in our model by comparing our data and performing different EDA (Exploratory Data Analysis) techniques on our target variable.

We started by analyzing three different datasets, each with its own set of features and target variables. Ashis's data had 36 columns, Chebrolu's had 27 columns, and my data had 14 columns. We performed Gradient Boosting and SVM on each dataset and compared the accuracy of our models.

After a thorough analysis, we found that my data had the highest accuracy in the Gradient Boosting model with a value of 1.0, while Chebrolu's accuracy was 0.1 and Ashis's accuracy was 0.6. In the SVM model, my data had an accuracy of 0.47. Based on these results, we decided to use my data for our final model, as it had the most accurate results in the Gradient Boosting model.

Here is a breakdown of the roles and responsibilities of each team member:


| Team member name         | Role and Tasks|
| :-------------: | :-------------: |
| Fatimah | Data preprocessing feature engineering and modeling |
| Chebrolu | Data cleaning and preprocessing, and feature engineering  |
| Ashish | Data preprocessing, feature engineering and modeling |
| Asif | Data analysis and preprocessing |
| Mohamed | Data analysis and preprocessing |


## Modeling


https://colab.research.google.com/drive/1WAL2YBiiAErggXLsJTTYQBi93sWD036b?usp=sharing


### Gradient Boosting classifier

<img width="410" alt="image" src="https://user-images.githubusercontent.com/123512564/221941696-afda8083-3ef1-4430-85dd-c3b2b036e533.png">


### Super vector machine model


<img width="407" alt="image" src="https://user-images.githubusercontent.com/123512564/221941466-3125d410-f054-4ee5-ae1c-fbcba4d1705e.png">










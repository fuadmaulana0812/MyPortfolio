# Credit Loan Prediction

### Objective
Objective of the project to predict whether someone is eligible for a loan or not. A person is said to be a good borrower based on a person's ability and history in repaying his loan. 

### Dataset
This is the description of all columns from [Credit Loan](https://docs.google.com/uc?export=download&confirm=&id=1qfKeXVzAFvvbgjPYrUOIBBYk0WrQ2bCf) dataset.
| Variable Name | Description |
| --- | --- |
| TARGET | (Target = 1 (Defaulters), Target = 0 (Good Loans) |
| ID | Customer ID |
| DerogCnt | Number Public Derogatories |
| CollectCnt | Collections |
| BanruptcyInd | Bankruptcy Indicator |
| InqCnt06 | Inquiries 6 Months |
| InqTimeLast | Time Since Last Inquiry |
| InqFinanceCnt24 | Finance Inquires 24 Months |
| TLTimeFirst | Time Since First Trade Line |
| TLTimeLast | Time Since Last Trade Line |
| TLCnt03 | Number Trade Lines Opened 3 Months |
| TLCnt12 | Number Trade Lines Opened 12 Months | 
| TLCnt24 | Number Trade Lines Opened 24 Months | 
| TLCnt | Total Open Trade Lines | 
| TLSum | Total Balance All Trade Lines | 
| TLMaxSum | Total High Credit All Trade Lines | 
| TLSatCnt | Number Trade Lines Currently Satisfactory | 
| TLDel60Cnt | Number Trade Lines Currently 60 Days or Worse | 
| TLBadCnt24 | Number Trade Lines Bad Debt 24 Months | 
| TL75UtilCnt | Number Trade Lines 75 pct Utilized | 
| TL50UtilCnt | Number Trade Lines 50 pct Utilized | 
| TLBalHCPct | Percent Trade Line Balance to High Credit | 
| TLSatPct | Percent Satisfactory to Total Trade Lines | 
| TLDel3060Cnt24 | Number Trade Lines 30 or 60 Days 24 Months | 
| TLDel90Cnt24 | Number Trade Lines 90+ 24 Months | 
| TLDel60CntAll | Number Trade Lines 60 Days or Worse Ever | 
| TLOpenPct | Percent Trade Lines Open | 
| TLBadDerogCnt | Bad Dept plus Public Derogatories | 
| TLDel60Cnt24 | Number Trade Lines 60 Days or Worse 24 Months | 
| TLOpen24Pct | Percent Trade Lines Open 24 Months |

### Preprocessing Data
At this stage I did several treatments such as handling missing values, imbalanced data, split data, and standardizing data. First, I checked any columns that have missing values. 

<img align="center" width="600" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/173ca168b0c34f32a8e0fa3a4562e44ec39f7a68/Projects/Loan%20Default%20Prediction/Credit%20Loan/Images/handling_miss_value.png"> 

The approach taken is to replace empty values with the average in each column. The goal is to maintain the distribution in each column and avoid adding variations to the data. Second, handling missing values. The target of the data consists of 2500 defaulter and 500 good borrowers. Good borrowers have little data which can result in the model not being able to accurately predict good borrowers.

<img align="center" width="500" height="150" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/1ab38d54dd055b6efc312ae2c2f918b74507f5e4/Projects/Loan%20Default%20Prediction/Credit%20Loan/Images/imbalanced_data.png"> 

The metric used is ROC AUC, this is because ROC AUC is very sensitive to imbalanced data. The highest ROC AUC was obtained when oversampling was 0.4 and under sampling was 0.6. The result of resampling is 1666 defaulters and 1000 good borrowers. Third, split the data into train and test with a ratio of 8:2. Then standardize the data with the aim of reducing the range that is too far for each observation.

### Modelling
I made 5 models for this project, namely Decision Tree, Random Forest, Extra Gradient Boosting, K-Nearest Neighbors, and Support Vector Machine. The following is the evaluation score of the 5 models

<img align="center" width="700" height="400" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/1ab38d54dd055b6efc312ae2c2f918b74507f5e4/Projects/Loan%20Default%20Prediction/Credit%20Loan/Images/model_compare.png">

Random Forest has the highest score for all metrics, so the best model is Random Forest. After that, look for the best hyperparameter to optimize the existing Random Forest model. The goal is to get a better model. I use grid search to find the best parameters.

<img align="center" width="600" height="400" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/1ab38d54dd055b6efc312ae2c2f918b74507f5e4/Projects/Loan%20Default%20Prediction/Credit%20Loan/Images/optimi_compare.png">

The original model has a score that is superior to the optimization model. then the final model taken is Random Forest (Original). Then I made predictions on the test data and got a score of 0.83. This model is good enough to predict whether someone is a good borrower or not.

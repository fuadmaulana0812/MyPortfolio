# Credit Risk

### Objective
Objective of the project to predict whether someone is eligible for a loan or not. A person is said to be a good borrower based on a person's ability and history in repaying his loan. 

### Preprocessing Data
At this stage I did several treatments such as handling missing values, convert to correct type, classify loan_status, find class weight, and split . First, I will deal with data that has missing values. I will drop columns that have missing values ​​more than 75% of the data. Then I dropped all rows of data that had missing values.

<img align="center" width="1000" height="200" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/afe79c75b7b0e2fb063855e489558b9d1a53d2f1/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/handling_missing_values.png"> 

After that, there are several columns that only have one unique value, then that column will be dropped. Second, convert the wrong column data type. These columns are
| Variable Name | Convert |
| --- | --- |
| term | string to integer |
| emp_length | string to integer |
| earlist_cr_line | string (date format) to integer (number of months until now) |
| issue_d | string (date format) to integer (number of months until now) |
| last_pymnt_d | string (date format) to integer (number of months until now) |
| last_credit_pull_d | string (date format) to integer (number of months until now) |
| other categorical column | LabelEncoder |

Third, classify loan_status. Before classifying, we have to check the value in loan_status.

<img align="center" width="1000" height="250" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/81112e6dcd591a3ce260ed47a43eaed9bd2a4fa7/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/loan_status.png">

Classify charged off, default, late (31 - 120 days) as bad borrower and current, fully paid, in grace period, late (16 - 30 days) as good borrower. Forth, find class weight. Check distribution of borrower status (which was previously loan_status).

<img align="center" width="1000" height="150" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/3418bb1800a8920163d69feb7078b92a234e1b74/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/borrower_status.png">

The borrower_status column has data that is not balanced, so you need to find the weight of the class/label. These weights will be used in modeling to overcome unbalanced data.

<img align="center" width="1000" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/3418bb1800a8920163d69feb7078b92a234e1b74/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/class_weight.png">

Fifth, split the data into train and test data with a ratio of 8:2.

### Modelling
I created a neural network model using TensorFlow. I created a neural network model using TensorFlow. I use 3 dense layers, Adam as optimizer, and use EarlyStopping.

<img align="center" width="1000" height="600" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/model_risk.png">

After that the model will be run.

<img align="center" width="1000" height="200" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/run_model.png">

The final epoch obtained has the following accuracy and loss.

<img align="center" width="1000" height="60" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/final_epoch.png">

Then you can also see how accuracy and loss move at each epoch.

<img align="center" width="400" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/accuracy.png">
<img align="center" width="400" height="300" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/loss.png">

Then make predictions on the test data and compare the predictions with y_test using the classification report.

<img align="center" width="1000" height="400" src="https://github.com/fuadmaulana0812/MyPortfolio/blob/99e72fdb0df065f2a1dc50508ae17ba535b18729/Projects/Loan%20Default%20Prediction/Credit%20Risk/Images/classification_report.png">

This model is very good because it has an accuracy of 0.98. Other metrics also have values ​​that are not much different, so the model is very good at predicting whether someone is categorized as a good borrower or not.

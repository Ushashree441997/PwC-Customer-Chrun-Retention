# PwC-Customer-Chrun-Retention
PWC Power BI Virtual work experience - Customer Churn Retention
# Table of Contents:
Problem Statement
Datasource
Data Preparation
Data Modeling
Data Analysis (DAX)
Data Visualization (Dashboard)
Insights

# View Customer Churn Retention Dashboard - 
https://app.powerbi.com/view?r=eyJrIjoiOWQ3MzJmMzktMjRlYS00YTNkLWE4MjAtOWJiNTQ5ZTI4OTRlIiwidCI6IjQ5NmE3ZmFlLTM0ZmUtNDJmNS1iNjYzLTc3MjFlNmZhYzA0MCJ9

# Problem Statement :
The purpose of this task is to:
Define proper KPI's
Create a dashboard for the retention manager reflecting the KPI's
Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
Customers who left within the last month
Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
Demographic info about customers – gender, age range, and if they have partners and dependents

# Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.
Customer Churn dataset is give table named:
Customer churn dataset which has 23 columns and 7043 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:
Replaced the value is SeniorCitizen N coverted No and Y converted Yes
In the new table, one additional conditional columns were added using M-formula:
loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")
Removed Unnecessary columns
Removed Unnecessary rows
Each of the columns in the table were validated to have the correct data type

# Data Analysis (DAX):
Measures used in all visualization are:

Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])

churn count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")

churn rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)

Dependent in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Device protection in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online backup in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

Online security in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

Partner in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Churn]="Yes"), 0)

Phone service in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

SenioCitizen in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"), 0)

Streaming Movies in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

Streaming TV in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

Tech Support in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

# Data Visualization (Dashboard):

![image](https://github.com/Ushashree441997/PwC-Customer-Chrun-Retention/assets/69711495/23ae35fd-5522-4fb8-9287-0010c59bbd8b)
![image](https://github.com/Ushashree441997/PwC-Customer-Chrun-Retention/assets/69711495/bca223b4-23b4-4a13-9a25-9a0181edfff4)
![image](https://github.com/Ushashree441997/PwC-Customer-Chrun-Retention/assets/69711495/b2d470cb-3736-45b2-a8ea-a9f3026d12a0)
![image](https://github.com/Ushashree441997/PwC-Customer-Chrun-Retention/assets/69711495/923864d2-a0b0-46ef-a4c4-bf9dcf229e8f)

# Insights:

Customers on the Two-Year contract, have been with the company for long, while most of the customers on Month-to-Month contract joined the company.

The company is at risk of losing recently joined customers. based on the results from analysis.. if they decided to month-to-month contract.

7043 customers are at the risk of churn. and The churn rate is 27% and yearly charges is $16.06M charges. and Monthly Charges is $456.12K monthly charges.

2955 tech tickets were opened and 3632 admin tickets were opened.

Most of the churned customers did not sign up for Online Security and tech support and also did not sign up for Phone Services.

It a lot of customers had an issue with Fiber Optic . Up to 42% of the customers churned were using Fiber Optic as their Internet Services.



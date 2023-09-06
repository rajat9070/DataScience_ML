# PWC Power BI Virtual work experience - Diversity and Inclusion Analysis
![PWC Diversity and Inclusion](https://github.com/rajat9070/DataScience_ML/blob/main/PWC%20Diversity%20and%20Inclusion/Homepage.JPG)

## Table of Contents:

- Problem Statement
- Datasource
- Data Preparation
- Data Modeling
- Data Analysis (DAX)
- Data Visualization (Dashboard)
- Insights

## Problem Statement :

The purpose of this task is to:

- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

Calculating the following measures could help to define proper KPIs:

- Number of men
- Number of women
- Number of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- % turnover 
- Average performance rating: men
- Average Performance rating: women

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and Diversity and Inclusion dataset:

Dataset: [PWC Diversity and Inclusion](https://github.com/rajat9070/DataScience_ML/blob/main/PWC%20Diversity%20and%20Inclusion/03%20Diversity-Inclusion-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:

- `Diversity and Inclusion dataset` which has `500 rows and 31 Column` of observation

Data Cleaning for the dataset was done in the power query editor as follows:
- Changed the header row of dataset
- Replaced  the value is `New hire FY20?` N coverted No and Y converted Yes
- Replaced  the value is `In base group for turnover FY20` N coverted No and Y converted Yes
- Replaced  the value is `Promotion in FY20?` N coverted No and Y converted Yes
- Removed Unnecessary columns 
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

## Data Analysis (DAX):

Measures used in  all visualization are:

- Count of Men = `COUNTX(FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"), 'Pharma Group AG'[Gender])`

- Count of Women = `COUNTX(FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"),'Pharma Group AG'[Gender])`

- Count of Leavers in FY20 = `COUNTX(FILTER('Pharma Group AG','Pharma Group AG'[FY20 leaver?]="Yes"),'Pharma Group AG'[FY20 leaver?])`

- % of hires men = `DIVIDE('Dax Measures'[Count of Men],('Dax Measures'[Count of Men]+'Dax Measures'[Count of Women]))`

- % of hires women = `DIVIDE('Dax Measures'[Count of Women],('Dax Measures'[Count of Men]+'Dax Measures'[Count of Women]))`

- % Promotion(FY20) = `DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY20?]),'Pharma Group AG'[Promotion in FY20?]="Yes"),COUNT('Pharma Group AG'[Promotion in FY20?]),0)`

- % Promotion(FY21) = `DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Promotion in FY21?]="Yes"),COUNT('Pharma Group AG'[Promotion in FY21?]),0)`

- % Turnover = `Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG','Pharma Group AG'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('Pharma Group AG'[Employee ID]),Filter('Pharma Group AG',NOT('Pharma Group AG'[Department @01.07.2020]=BLANK()))),2))`

- % Women promoted = `DIVIDE(CALCULATE(COUNT('Pharma Group AG'[Gender]), 'Pharma Group AG'[Gender]="Female",'Pharma Group AG'[Promotion in FY21?]="Yes"), CALCULATE(COUNT('Pharma Group AG'[Gender]),'Pharma Group AG'[Promotion in FY21?]="Yes"), 0)`

- %hier Men(FY20) = `DIVIDE(CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]),'Pharma Group AG'[New hire FY20?]="Yes",'Pharma Group AG'[Gender]="Male"),CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]),'Pharma Group AG'[Gender]="Male"),0)`

- %hier Women(FY20) = `DIVIDE(CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]),'Pharma Group AG'[New hire FY20?]="Yes",'Pharma Group AG'[Gender]="Female"),CALCULATE(COUNT('Pharma Group AG'[New hire FY20?]),'Pharma Group AG'[Gender]="Female"),0)`

- Avg Performance Rating Men = `CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"))`

- Avg PerformanceRating Women = `CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"))`

- New Hire Count = `COUNTX(FILTER('Pharma Group AG','Pharma Group AG'[New hire FY20?]="Yes"),'Pharma Group AG'[New hire FY20?])`
  

## Data Visualization:

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Diversity and Inclusion:

| Dashboard 1 |
| ----------- |
|![PWC Diversity and Inclusion](https://github.com/rajat9070/DataScience_ML/blob/main/PWC%20Diversity%20and%20Inclusion/Dashboard-1.JPG)|

| Dashboard 2 |
| ----------- |
| ![PWC Diversity and Inclusion](https://github.com/rajat9070/DataScience_ML/blob/main/PWC%20Diversity%20and%20Inclusion/Dashboard-2.JPG)|

## Insights:

As shown the data Visualization, It can be deduced that:
| ----------- |
| ![PWC Diversity and Inclusion](https://github.com/rajat9070/DataScience_ML/blob/main/PWC%20Diversity%20and%20Inclusion/Insights.JPG)|


---

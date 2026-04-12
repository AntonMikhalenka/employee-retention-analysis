# Salifort Motors Employee Retention Analysis
## Overview
Salifort Motors is experiencing high employee turnover. This project analyses HR data to identify the key drivers of turnover, and to find a way to identify employees at risk. This would help HR take proactive action to improve retention.
## Data
HR dataset was provided as part of the Google Advanced Data Analytics certificate program. It contains 14,999 employee records with 10 features. The dataset is available on [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). Download and place in the root folder.
## Key findings
- Satisfaction level is the primary predictor of turnover. Leavers reported significantly lower satisfaction (0.44 vs 0.67).
- Three distinct employee archetypes were identified. The first one consists of underperformers with low satisfaction and low workload - disengaged and mentally checked out employees. The second group represents high performers with heavy workloads and low satisfaction - employees who have burned out. The third, least visible, group shows high performers with high satisfaction despite heavy workloads, potentially leaving due to better external opportunities or undetected dissatisfaction.
- Both leavers and stayers work significantly above standard hours, averaging 208 and 199 hours per month respectively - approximately 25-30% above the standard 160-170 monthly hours, suggesting overwork is a company-wide issue rather than isolated to employees who leave.
- Many employees with high workload and 5-7 projects tend to leave the company after 3-5 years of tenure, possibly due to growing dissatisfaction with lack of career progression.
## Model
For the analysis a Random Forest Classifier has been chosen. The main reasons were:
- EDA showed that relationships between variables and turnover are non-linear. 
- Multiple distinct leaver clusters and U-shaped patterns were found across several variables - Random Forest handles these kinds of patterns well.
- Random Forest provides feature importance scores, which helps understand what drives turnover.
- Random Forest handles the class imbalance (83/17) using class_weight='balanced'.

The final version of the model had the following scores: **F1** for leavers - **0.93**, **ROC-AUC** - **0.981**. The confusion matrix showed that on the test data the model correctly identified **368 out of 398** actual leavers and only **29** employees were flagged incorrectly as being at risk.
## Recommendations
- **Satisfaction levels** should be closely monitored - especially among employees with high workloads and 5-7 projects.
- **Salaries** should be reviewed - low earners leave at 20.5% compared to 4.8% for high earners.
- **Workload** should be addressed company-wide. Both leavers and stayers average well above standard monthly hours (208 and 199 respectively compared to a standard 160-170).
- Particular attention should be paid to employees with 5-7 projects and 3-5 years tenure - highest risk group identified in EDA.
- The **promotion pipeline** should be reviewed - only 2.1% of employees promoted in 5 years, likely driving dissatisfaction among high performers.
## Technologies used
Python, pandas, numpy, matplotlib, seaborn, scikit-learn
## How to run
- Clone repo
- Install dependencies: pip install -r requirements.txt
- Open and run notebook/salifort_motors_analysis.ipynb

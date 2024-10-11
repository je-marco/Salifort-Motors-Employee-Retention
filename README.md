# Providing Data-driven Suggestions for Human Resources to Increase Employee Retention


## Overview
[Link to the Executive summary](https://docs.google.com/presentation/d/1Lcxk6ODA_UuiC2HJNIebM-Nfddu4N4nelW2qAsNsCzE/edit?usp=sharing)

The goal of this project is to analyze the employee dataset and build a predictive model that can provide insights about turnover of Salifort Motors (* a fictional company*) employees. For the purposes of this project, the employee turnover data includes both employees who choose to quit their job and employees who are let go. 

The XGBoost outperforms the other models.  It achieved an AUC score of 90.43% on the test set, which means that the model is highly capable of distinguishing between employees who will leave and identify influential factors that contribute to their leaving. The insights from this model will help HR to make decisions to increase employee retention. 


## Business Understanding   
The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company and answer the question: **"What's likely to make the employee leave the company?"** 

They surveyed a sample of employees, but now they don't know what to do with the collected data. HR asked for help with the following goals in mind:
1. Analyze the data
2. Build a model that predicts whether or not an employee will leave the company
3. Provide data-driven suggestions to improve employee retention

The reason for the predictive model is that if the model can predict employees who are likely to quit, it is also possible to identify factors that contribute to their leaving. A good model will help the company increase retention and job satisfaction for current employees, and save money and time training new employees. 

## Data Understanding

The [data](https://github.com/je-marco/Salifort-Motors-Employee-Retention/blob/35ba2a76da0e1d6cbd07b182b0cb9f98c27e8f27/HR_capstone_dataset.csv) came from a survey that was given by the HR department to a sample of employees. It contains 15,000 rows—each representing one unique employee and 10 columns for the variables. The dataset contains variables that are predictive of whether the employee will leave or not, such as the employee's average monthly hours, number of projects, department, satisfaction level, last evaluation score, etc. 

The figure below show the distribution of the target variable, employees who left/stayed in the company: 

![pie chart](https://github.com/je-marco/Salifort-Motors-Employee-Retention/blob/7166cf950546d0b5e77bb347047ff779d23fbb7b/left_distribution.png)


## Modeling and Evaluation
The data leakage issue was addressed, and actions were taken to minimize its effect: a model with an unrealistic evaluation score that is not replicated during production. To develop a realistic model, fewer features that would be legitimately available during the actual use of the model were taken into account. Also, features that are highly correlated to the target variable were eliminated or transformed.

After conducting feature engineering, the extreme gradient boosting (XGBoost) was chosen as the champion model. On the test set, it achieved an AUC score of 90.43%, which means that the model is highly capable of distinguishing between employees who will leave or stay in the company. Also, the model is a reliable tool for identifying the influential factors behind employee departure and, therefore, a valuable tool for HR in increasing employee retention.

**Feature Importance:**

![feature_importance_plot](https://github.com/je-marco/Salifort-Motors-Employee-Retention/blob/5db984f0530dfe6d2f9c57e7fb9fe3cb4edbd5c7/feature_importance_3.png)

The plot above shows that `tenure`, `number_project`, `salary`, and `overworked` are the most helpful in predicting whether an employee will leave or stay in the company.

**Confusion Matrix:**

![confusion_matrix](https://github.com/je-marco/Salifort-Motors-Employee-Retention/blob/a66e80d57e5ccf2bcf24bea3267fd4e8fbc12c96/Confusion_Matrix_xgb3.png)

The model tends to predict more false positives (91) than false negatives (58). This shows that the model may identify that some employees will leave the company when, in reality, they will stay.

Regardless of this tendency, it is important to emphasize that the model is still a reliable tool for understanding and developing a solution to employee turnover.

## Conclusion and Recommendation
The results of exploratory data analysis and the modeling effort revealed that employees at Salifort Motors are overworked.

To improve employee retention, consider the following recommendations:
* According to Gallup, about 80% of employees who felt criticized or unmotivated after a performance review started to look for a new job. That is why a more standardized evaluation review is important. Consider making the evaluation review a collaborative and dynamic process that seeks to better the relationship between an employee and a manager. 
  
* Reward and recognize employees who contribute more or put in more effort. For instance, either reward employees for working longer hours, or don't require them to do so. 
  
* Set a limit on the number of projects that employees can work on and regularly check in with employees to ensure they are not overworked and address any issues promptly.

* Consider promoting employees who have been with the company for at least four years, or conduct further inquiry about why four-year tenured employees are so dissatisfied.

* Regularly benchmark salaries against industry standards to ensure competitiveness. 
  
* Conduct company-wide and team-specific discussions to understand and assess the company work culture both generally and in specific contexts.

* Regularly conduct employee engagement surveys to gather feedback and identify areas for improvement

## Note
*Throughout this project, you'll see references to the problem-solving framework, PACE. The [python notebook](https://github.com/je-marco/Salifort-Motors-Employee-Retention/blob/7f4b06e5d394c2eb1e71133a753e29d5421369b6/employee_retention_Salifort_Motors.ipynb) components are labeled with the respective PACE stages: Plan, Analyze, Construct, and Execute.*






# Links
* [Project Proposal](https://docs.google.com/document/d/1Lu8Xjy_Gln6fJE_xKtN3JI-zWIcQvUAMUfO61aF2cA8/edit?usp=sharing)
* [Data Dictionary](https://docs.google.com/document/d/18CXxnQRMamqqLPXl-m1_sd-bLHcW_NMaV7KiJnAzBBg/edit?usp=sharing&resourcekey=0-Z_RwGG93DpmMxoU8LtIKEg)
* [PACE Strategy Document](https://docs.google.com/document/d/13KlrtnZA52hJyGrw6ii5F1e5I6McgeJIDBWSDiuleOQ/edit?usp=sharing&resourcekey=0-12zdTVBLHYeVLcB0DO-FOQ)

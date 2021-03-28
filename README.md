# Predicting Employee Attrition Using Classification Models

**Author**: [Matt Schwartz](mailto:mtschwart@gmail.com)

## Overview 

The following report provides data and analysis on an employee dataset created by IBM data scientists. Below, I'll discuss the classification models used to help predict employee attrition based on various features about each employee.

## Business Problem

Employee attrition is one of the more costly recurring expenses at any company. Not only are you losing the institutional knowledge that person has learned on the job which makes them very effective (especially if they've been on the job for a number of years), but you are also paying for lost productivity, and the time it takes to hire someone new, as it prevents current employees from fully doing their own jobs. According to [IBM](https://toggl.com/blog/employee-attrition), the cost of attrition can be 1.5x the salary of the employee who left, and for a mid-size company, up to $6.75 million a year.

Any profit-maximizing firm would want to reduce attrition. Lower attrition is less costly, and generally means that your employees are happy, and in turn, productive. HR data is an extremely valuable resource and can be highly advantageous to companies who take time to learn it. Employees tend to be a company's most important assets, and understanding the factors causing them to leave is invaluable.

This project will go into what factors lead to employee attrition, using an employee dataset from IBM. We are hoping to develop a model that results in a very low **false negative rate**. This would mean our model rarely misses employees who decide to leave. In practice, this model could be used to help employers address areas making employees unhappy and unproductive, and which ones are most likely to leave. This will provide them with the data to step in and support employees before the leave and develop better HR policies that make employees feel welcome.

## Data

The data, created by IBM data scientists, comes from Kaggle. There are 1470 rows, each representing one employee. There 30 attributes for each employee, and whether they left the company or not. Some of these attributes are:

- Age
- Job satisfaction
- Education
- Total working years
- Job role
- Distance from home
- and monthly income

Using these features, I will test out different classification models and fine-tune the model that best reduces the false negative rate (best recall score).

## Methods

To build a prediction engine, we utilized classification models. These models are used when the target variable is binary. In this context, attrition is the target and can only be yes or no. Four models were tested with varying degrees of success:

 - Logistic Regression
 - Naive Bayes (Gaussian)
 - Decision Tree
 - XGBoost

## Results

Logistic regression provided the best overall results with respect to recall score. The model misclassified only 9 employees who actually left the company, a false negative rate of 2.4% (recall score of .85). Overall, the model correctly predicted 65% of employees. The best model in terms of overall prediction was XGBoost, as it classified 86% of employees correctly, but had only a .28 recall score (12% false negative rate).

## Conclusions

Our final model has good predicitive power - as mentioned above, it accounts for over 80% of the variation in price - but does have some issues. It's very heteroscedastic, meaning the residuals are not randomly distributed, and the root mean squared error, although much smaller than we started, is still $85K, meaning that each prediction has an average error of $85K. There is future work to be done. 

## Further Analysis

In the real world, our modeling here can help companies address issues employees have with their job before the decided to leave (or poor performance ends up in being let go). An employer can hopefully identify which employees they could be at risk of losing, and properly invest resources into retaining them and making them happier. The logistic regression model identified the following five features as the most important in predicting attrition:

- Years since last promotion
- Frequent business travel
- Working overtime
- Distance from home
- Job role = Sales representative

In terms of future work, I'd like to gather more data across different industries. 1500 employees is a small sample and is likely contributing to our issues of overfit in our tree-based models. Having good samples from various types of work can provide extremely useful data and a wholistic view of why employees leave.

I'd also want to ensure that this model and the data behind it is used ethically. For example, gender and race should probably be exluded from any model as to avoid bias from employers. [According to the Center for American Progress](https://www.americanprogress.org/issues/economy/reports/2019/12/05/478150/african-americans-face-systematic-obstacles-getting-good-jobs/), Black workers face far higher unemployment rates than white workers, and when they do get jobs, they're paid systematically less than white employees. In addition, Black workers earn fewer benefits and work in less stable industries than white workers. Data scientists developing machine learning algorithms in this space (and across ML applications) must work to remove biases from their models. Future work on this model should focus on not introducing racial or gender bias into the model, and ensure that employers can't abuse this model and use it as an excuse to fire employees they do not like.


## For More Information

Please find the full analysis in the Jupyter notebook contained in this respository.

For any questions, please contact Matt Schwartz at [mtschwart@gmail.com](mailto:mtschwart@gmail.com)



## Repository Structure

```
├── data
├── images
├── .canvas
├── .gitignore
├── CONTRIBUTING.md
├── Predicting_Employee_Attrtion_Phase_3_Project.ipynb
├── Predicting_Employee_Attrtion_Phase_3_Project_Jupyter_Notebook.pdf
├── Predicting_Employee_Attrtion_Presentation.pdf
├── README.md
```

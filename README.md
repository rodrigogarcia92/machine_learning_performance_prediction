# Machine Learning for Performance Prediction
Python Notebook: [performance_prediction_script.ipynb](https://github.com/rodrigogarcia92/machine_learning_performance_prediction/blob/4602b1acedd7d75ddcbe905f8fbba75db8de27f3/performance_prediction_script.ipynb)

## Scope of the Project
The public education sector in Peru is under the Ministry of Education (Minedu) 's national governance. However, 26 Regional Offices and 222 Local Education Management Units (UGELs or Unidades de Gestión Educativa Local) are responsible for various functions and responsibilities, such as enrolling students, hiring teachers, distributing books, addressing bullying and violence cases, among others.

The CdD (Comrpomisos de Desempeño) program evaluates the performance of the UGEL through indicators. This performance can be measured with a number of metrics, such as the mean achievement score in a year, or the percentage of indicators where the UGEL reaches the goal. In this brief analysis, I intend to predict the performance of the UGEL and find the key factors that affect these institutions' ability to do a good job.

For these Project, I used Machine Learning in Python, including the basic libraries Pandas, NumPy, SciPy, and Scikit Learn, as well as MatplotLib and Seaborn for some visualizations.


## Data Used
The dataset used was built and cleaned beforehand using R. The data encompasses different years of CdD results, as well as information about the UGEL and their jurisdictions. Every dataset used is public and can be found on the Ministry of Education website.


## Methodology
I used machine learning to train and test various models, encompassing Linear Regression, Lasso and Ridge Regressions, Support Vector Regressors (SVR), as well as Random Forest and Gradient Boost Regressors for this project. I used the Adjusted R2 for the test dataset to compare the models.
![image](https://github.com/rodrigogarcia92/machine_learning_performance_prediction/assets/132176209/eaac3931-ccd3-4a7d-b2e3-19e77c4ec5de)

The different "yn" variables (y1, y2, ... y5) represent distinct performance measures:

y1: "desv_mean_achievement" signifies the deviation of the mean achievement score of a UGEL in relation to the mean score of all UGELs in a given year.
y2: "target_met_perc" corresponds to the percentage of indicators assessed within a UGEL where the UGEL achieved the targets set by the Ministry.
y3: "delta_achievement" quantifies the year-over-year fluctuations in the mean Achieved Score of the UGEL when evaluated in the CdD.
y4: "delta_target_met" measures the year-over-year variations in the percentage of indicators assessed within a UGEL where the UGEL met the target.
y5: "desv_target_met" assesses the deviation in the percentage of indicators assessed within a UGEL where the UGEL achieved the target concerning the annual percentage.

It became evident that variables like "target_met_perc" and "delta_achievement" hold the highest potential for developing a successful machine learning model. Such a model could significantly enhance our comprehension of each UGEL's performance and may even allow us to make predictions about how these institutions will fare in the future.

Finally, I conducted a comprehensive Grid Search, exploring various models and parameters, with the objective of identifying the optimal model that will guide our future efforts, still using the Adjusted R2 for the test dataset in each model


## Results

Overall I was happy with the results, as the Adjusted R2 was very high given this is real data. The best model trained for predicting the Target Met Percentage (target_met_perc) was a Gradient Boost Regressor out of the box, while the best model for predicting the Variation of Performance (delta_achievement) was a Random Forest Regressor. In both cases, I achieved the models had an Adjusted R2 score close to 0.6.

### Model to predict Target Met Percentage
![image](https://github.com/rodrigogarcia92/machine_learning_performance_prediction/assets/132176209/6e365875-f6c3-4f33-98d0-3daede19d396)


### Model to Predict the Variation of Performance
![image](https://github.com/rodrigogarcia92/machine_learning_performance_prediction/assets/132176209/ee6894c6-2256-4b5b-98e8-a134b9e7d0e1)



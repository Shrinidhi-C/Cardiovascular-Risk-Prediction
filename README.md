# Cardiovascular-Risk-Prediction
The classification goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD).  The dataset provides the patients’ information including over 4,000 records and 15 attributes which are demographic, behavioral, and medical risk factors. The dataset is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts.


Considering the reliable data available, that indicates disease incidence rates/risk factors,
exploratory and predictive analysis is done in order to predict the 10-year risk of coronary heart
disease.

Starting with the data pre-processing that includes missing values analysis, wherein the missing
values in data are imputed with appropriate aggregate values while avoiding any data redundancies.
The outliers are left unhandled considering the possibility of them being the potential risk factors.
The correlation between the dependent variable and the features is checked. Also, the dependency
between the risk factors is exploited to handle the multicollinearity by imputing a new feature- Pulse
Pressure to replace the dependent ones- Systolic and Diastolic Blood pressure.

![image](https://user-images.githubusercontent.com/57758182/211598570-b41ab3ec-931d-4540-acce-232ea4281985.png)


The exploratory data analysis explains the type of classification and imbalance in class. It also
shows the vulnerability of patients to disease based on the risk factors. The analysis helped
understand the contribution of risk factors in predicting the risk. The following analysis can be drawn
from the analysis:

● There is skewness present in most of the continuous feature distributions.

● Most of the patients possess education of level 1. The risk of coronary heart disease is
maximum in patients of education level 1, followed by patients of education level 4, 3, 2.

● Female patients of age group (49-62) and Male patients of age group (48-60) are vulnerable to
the risk of CHD( coronary heart disease).

● The count of female patients is more. The average age of risk of CHD is higher in female
patients. Overall, the risk of coronary heart disease is higher in male patients by 6%.

● There are an almost equal number of patients who smoke and who don’t. The risk of disease is
slightly higher in smokers (by 3%).

● Patients who are on blood pressure medication have a significantly higher risk of coronary
heart disease i.e., 33%.

● Prevalent stroke is rarely seen in patients. But the risk of coronary heart disease among them
is significantly higher (45%), which is 31% higher than the others.

● Hypertension is seen in many patients (~800). Patients with prevalent hypertension are at
higher risk by 12%.

● Out of the very few patients diagnosed with diabetes, 37% of them are at risk of coronary
heart disease.

● The type of heart_rate doesn't seem to affect the risk of coronary heart disease significantly
whether it is low, normal, or high.

A null hypothesis is proposed and essential features are identified and selected based on statistical
methods- Chi-Square and ANOVA F-test score p_values that quantify the prospective relation
between features and the target variable. Feature importance study shows that age is one of the most
important factors in predicting the risk of the disease. Followed by pulse pressure, glucose, and so on.
Further oversampling is done in order to balance the data using one of the data augmentation
techniques called SMOTE. Skew transformation, encoding, and scaling are considered to prepare the
data for modeling.

Various classification algorithms like the following are experimented with to bring in the prediction
along with various hyperparameter tuning techniques namely GridSearchCV, RandomSearchCV, and
BayesSearchCV to fine-tune the parameters.

● Logistic Regression

● Decision Tree

● Random Forest

● Support Vector Machine

● K-Nearest Neighbors

Finally, and importantly, the utility of risk prediction algorithms is assessed in the context of the
clinical environment, in order to do justice to the imbalance and the type of problem at hand.
Therefore considered to maximize the recall score while having a reasonable ability to distinguish
between the classes as indicated by the ROC_AUC score.

The conclusion is that the Random Forest Classifier model with Bayesian optimization(for
hyperparameter tuning) can be considered the most optimal model among the ones that are experimented with. It predicts a pretty high recall score of (0.7046) while having a reasonable capacity
to distinguish between the classes indicated by (ROC_AUC= 0.71).

Although the recall and roc_auc for discrimination are most often presented, it could be argued
that model calibration (‘goodness of fit’) is a more clinically relevant measure of model performance,
as clinician and patient want to know if the predicted risk resembles the actual risk.
Since it seems right to apply the oversampling techniques only on train split and go for prediction rather than
including the synthesized samples in test data to overestimate the results. However future
improvements may include attempting to collect more data on minority class that helps the
analysis to be improved further.

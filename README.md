# GE-Customer-Churn-Project by Adam M. Lang
This is the final capstone project for my Masters Degree in Data Analytics from Southern New Hampshire University (SNHU). The project is based off a dataset obtained from General Electric (GE) for mobile phone customers churning to other wireless carriers. The background of this is that GE recently invested money in the healthcare AI application market for smartphones and their mobile customers were using the smart phones to access the AI applications. The concern is that customers were churning to other wireless carriers and not using their phones or the applications. Since the market for healthcare AI applications is a billion dollar industry they do not want to lost these customers. It also costs 5-10 times more to add new customers than to retain old customers. A recent study pointed to the fact that if you can reduce churn rates by 5% you can increase your profits by 85% and this was the premise of this study. 

The pilot evaluation of this data set consisted of using the R-Rattle GUI data mining tool. A logistic regression model was run and variables were selected for the model using multiple ANOVA tests. Multiple variables were identified that lead to churn including an interesting finding that the number of phone calls made to the retention team had a direct correlation to whether the person churned or not. However, the model had poor predictive capacity with an AUC value from the ROC curve of 0.64.

The pilot model was revised then with the following considerations: 
1. The target variable (CHURN) was significantly imbalanced and would have to be resampled. The SMOTE technique would be used in RStudio. 
2. There were significant data quality issues including 501 missing values, a factor variable called "CSA" with 277 levels, and multiple other factor variables with multiple levels and uneven distribution. There were numeric variables with skewed distributions as well. Plan was to drop the missing variables as they were coming from a variable that was not relevant to the data set. 
3. Model comparison: A logistic regression model would be run against a random forest model and compare the outcomes for independent variable selection and variable significance for churn prediction. 
4. Independent variable selection: this was a challenge with logistic regression and ANOVA. Three techniques would be used for the revision: Lasso regression, Stepwise regression, and Random Forest variable importance. The ANOVA was found to violate 3 variables for its use. 
5. Hard coding in RStudio would be used instead of the Rattle GUI as data manipulation and modeling would be easier and less rigid. 
6. 10 folds cross validation would be used to compare model outcomes and expose models to unseen data. In addition precision recall curves would be used for model validation. 

Final Outcomes:
1. A total of 8 logistic regression models were run. These were 4 models as well as a stepwise regression for each model. The best model of these was the LR model with variables selected from the random forest model and using a re-balanced CHURN target variable. The AUC value improved to 0.78 and the recall was 1.0.
2. Lasso regression was also utilized and performed almost as well as the best LR model. 
3. Random Forest modeling was performed with rebalanced CHURN variable and the unbalanced churn variable. The best outcome was with the rebalanced target variable. The AUC value was 0.87 and had the best predictive capacity. The recall was also 1.0. 
4. 10 folds cross validation revealed that the random forest classifier with re-balanced data was the best overall model. 
5. Important independent predictor variables indentified included: Income levels, Credit Rating, and number of calls made to the retention team. Also a significant amount of variables were identified related to use of the cell phone technology. 

In the final assessment of this modeling endeavor, it was determined that we could create customer profiles out of these findings. What does that mean? 
1. Using Income and Credit Levels we could extract a rating system that would correlate prediction of Income/Credit levels with churn probability. 
2. Phone data could be used to predict customer churn and again create a profile rating system. Variables such as: calls made to the retention team, changes in use of the phone (i.e. outgoing calls, voicemails, etc.) would identify high churner probability vs. low probability. 
3. Further research would have to be done looking at the correlation of healthcare app usage related to phone usage. 



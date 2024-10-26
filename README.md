# Report: Predict Bike Sharing Demand with AutoGluon 
#### Author: Mahima Chakraborty

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
There were 47 negative predicted values and Kaggle would not have accepted those predictions so all the negative values were to be changed to zero before submitting the results

### What was the top ranked model that performed?
The top ranked model in all the three runs was WeightedEnsemble_L2 with the highest score as depited in all three run summaries
## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
A correlation analysis showed significant correlation between temp and atemp, so I dropped the atemp column from the dataset. Also, the datetime column was split into separate columns of year, month, day, and hour.

### How much better did your model preform after adding additional features and why do you think that is?
After ading the new features, there was a significant improvement in the final kaggle score. This might be because the model was able to capture significant information or patterns from the separated columns of year, month, day, and hour, which it could not previously, when it was in the yyyy-mm--dd--hh:mm:ss format in one column. 
By dropping the atemp column that was highly correlated to the temp column, redundancy was reduced. So the model complexity might have been reduced making the training process more efficient.

## Hyper parameter tuning
### How much better did your model perform after trying different hyper parameters?
There was not a significant change in the model performance after hyperparameter tuning. The score changed from 0.53 to 0.50. It was better but not significantly better.

### If you were given more time with this dataset, where do you think you would spend more time?
I was unable to spend much time on the dataset because I have my exams coming up. However, if I had more time, I would have thought of more features that I could add and tried to improve the score as much as possible by focusing on EDA and finding out hidden relationships within the data.

### Table showing the models run, the hyperparameters modified, and the kaggle score obtained
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|default values|default values|default values|1.80|
|add_features|default values|default values|default values|0.53|
|hpo|GBM: num_leaves: lower=26, upper=66|XGB: max_depth lower=5, upper=9|refit_full='best'|1.50|

### Line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary
To summarise, this project enabled me to learn more about AutoGluon which I have never used before. I also became familiar with the AWS Sagemaker platform. The aim of the project was to predict how many bikes were leased in a given hour and I was successfully able to perform the tasks as per the instructions given in the notebook. I faced some problems during the execution of the code but was able to solve it by brainstorming and trying out new pieces of code, enabling me to learn how to troubleshoot problems while coding.

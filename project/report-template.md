# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Pedram Hashemi

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I had to find out how to add the parameters, besides that nothing happened. The negative values were also a problem but we set them to zero from the very beginning.

### What was the top ranked model that performed?
WeightedEnsemble_L3
That was the model after feature engineering. I did a very light feature engineering. but I suppose it will be much better and much faster if I remove some other variables and do a one-hot-necoding on some others.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
- Some Variables like season, holiday, workday are categorical and can actually be one-hot-encoded.
- the date variable can be split into day, month, year, hour
- workday and holiday variables don't seem to be complementary from the graph but from the name can be complementary. that means when one is zero, the other one is 1 and vice-versa.
- 

### How much better did your model preform after adding additional features and why do you think that is?
It got a lot better. some of the features got a better form. especially the categorical ones and the datetime features. because the got the right format that can be handles differently. Datetime feature is not handlable unless we split it.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
It didn't get much better. The biggest problem is the strategy to tune the hyperparameters. I suppose the model automatically searches the hyperparameters efficiently. The best model has no hyperparameters or at least I don't didn't find the documentation for it. I tried to tune the XGB model using the documentation I found here(https://auto.gluon.ai/dev/api/autogluon.tabular.TabularPredictor.fit.html). but it didn't change much.

### If you were given more time with this dataset, where do you think you would spend more time?
longer training time would definitely work better. maybe the model would find better models for the dataset. Hyperparameter tuning would come next. once I know which model performs best I would use hyperparameter tuning to find better hyperparameters for the same model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time_limit|presets|hpo|score|
|--|--|--|--|--|
|initial|600|best_quality|-| 1.80281 |
|add_features|600|best_quality|-| 0.64955 |
|hpo|600|best_quality|XGB:hyperparams| 1.34393 |



### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score.png)

## Summary

We ran 3 models.
all models for 600 seconds.
once without parameters and feature engineering.
once with feature engineering
once with feature engineering and hyperparameter tuning.

The model after feature engineering would work much better if more features are improved.
The model with hyperparameter tuning did not improve much.


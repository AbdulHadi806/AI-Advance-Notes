# Preprocessing and Training Techniques

# Basic steps to do in each project(for beginners)
- Read the dataframe
- Print the dataframe
- Plot the dataframe
- Check for correlation
- Check if you can create more features that may be more correlated
- Encode the categorical labels
- Normalize the dataframe
- Apply Regression or Classification according to your need

## Training
### Cross-validation
Cross-validation is dividing the whole dataset into multiple subsets and training them one by one and evaluating them.

### Grid Search
It is a technique that searches for the best hyperparameters, these hyperparameters can be how many decision trees there should be, the learning
rate, and much more. All we need to do is to tell which hyperparameters we want to experiment with and what values to try out, and it will evaluate all
possible combinations of hyperparameter values using **cross-validation**. For example, the following code searches for the best combination of hyperparameter
values for **RandomForestRegressor**

```
from sklearn.model_selection import GridSearchCV
param_grid = [
 {'n_estimators': [3, 10, 30], 'max_features': [2, 4, 6, 8]},
 {'bootstrap': [False], 'n_estimators': [3, 10], 'max_features': [2, 3, 4]},
 ]
forest_reg = RandomForestRegressor()
grid_search = GridSearchCV(forest_reg, param_grid, cv=5,
 scoring='neg_mean_squared_error')
grid_search.fit(housing_prepared, housing_labels)
```
Grid Search is useful when we are exploring relatively few combinations. However when the hyperparameter search is large, it is often preferable
to use **RandomSearchCV** instead. This class can be used in much the same way as the **GridSearchCV**, but instead trying out all possible combinations, it evaluates the given number of random combinations by selecting a random value for each hyperparameter at each iteration. This approach has two benifts:
- If we let the randomized search run for, say, 1000 iterations, this approach will explore 1,000 different values for each hyperparameters (instead of just a few values per hyperparameter with the grid search approach).
- We have more control over the computing budget we want to allocate to hyperparameter search, simply by setting the number of iterations.

## Techniques

### Bootstrap Sampling
It is the method where random samples of data are drawn with replacements from the original dataset. This means that each sample can contain 
duplicate instances of the original data, and some instances may not be included at all. This process results in multiple datasets (bootstrap samples)
of the same size as the original dataset.

### Bootstrap Aggregating(Bagging):
Bagging in terms of Random Forest is the technique of training multiple decision trees on different bootstrap samples of the training data and averaging their predictions to improve the model's accuracy and reduce overfitting.

### Boosting
Boosting is the technique in which we train multiple models and each model trained performs better than the previous model. In boosting we can create
multiple decision trees and this technique assigns weights to each model result on the basis of accuracy and results are given according to it.

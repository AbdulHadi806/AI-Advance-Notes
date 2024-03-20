# Preprocessing and Training Techniques


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

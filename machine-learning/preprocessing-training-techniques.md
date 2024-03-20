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

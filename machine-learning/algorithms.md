# ML Common Algorithms

[More Advance Notes to refer to](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials)

## Classifiers

### Multilabel classification

Multilabel classification is the type of classification in which we need to predict more than one class for example an image where you need to predict
people. The image has 2 people and we need to predict there names(data of those people have already been provided) then what the model will do is that it will have to predict 2 classes for example, Ali and Ahmed. Let's say now we want to check if Ali, Ahmed and let's say Sam is in the picture, our model will say [1,1,0] meaning [1=ali, 2=ahmed, 3=sam]

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/f7b0f9c2-b835-464d-90aa-f6b117288ed4">

### Decision Tree Classifier

A decision tree takes the best feature and creates a decision node based on that feature. Then the data is split into two branches based on whether the samples satisfy the condition of that feature or not. The decision tree has low Bias and High Variance.

**Low Bias** Model is trained well on the training dataset. Training gives fewer errors.

**High Variance** When the model is given new data than it may give larger errors.

#### Recommended theoretical Notes by sequence

[1) Decision Tree](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials/blob/main/decision%20tree.pdf)

[2) Post Prunning And Pre Prunning](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials/blob/main/Postprunning%20and%20preprunning%20decision%20tree.pdf)

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/ec9b2d47-7c04-430f-9930-fba4b7ade618">

<img width="400" alt="image" src
  ="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/8e03d9ab-61db-4805-a793-45b83220c5b5">

### Random Forest Classifier

In Random Forest Classifier, we take random rows from the subset and provide it to the decision trees, Random Forest Classifier has low variance and high Bias

Random Forest Increases Bias while decreases variance because of the term averaging, in random forest majority of trees' answers are taken as output.

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/d87e59ca-c1e1-461a-b432-64d45b7b51b3">

### Gradient Boosting Classifier

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/02bae323-5769-405b-8e0d-05459f673c1f">

### One vs all(OvA) and one vs one(OvO)
Many classification algorithms are unable to do multiple classifications so thus multiple classification models are created e.g logistic regression. In
such a case each model is trained to classify one category e.g cat or not. Another approach is one vs one in which models are created for classifying binary categories e.g cat and dog classifier then cat and lion classifier then lion and dog classifier.

In some situations, One vs all classification is required while in some one vs one is required.

One disadvantage of one vs all is that it is slow when working with large datasets, because for example if there are 10000 rows and 3 target categories then the data will be re-read as much as 30000 rows.

## Regression

### Polynomial Regression
Polynomial Regression is an advanced version of Linear Regression. Polynomial Regression is used when data is too complex. In polynomial Regression, we create new features from existing features by taking the square root, cube root, etc depending upon the degree.

```
from sklearn.preprocessing import PolynomialFeatures
poly_features = PolynomialFeatures(degree=2, include_bias=False)
X_poly = poly_features.fit_transform(X)

lin_reg = LinearRegression()
lin_reg.fit(X_poly, y)
```

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/197e1951-cc96-410a-b846-bcbe347efa0d">

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/358202a2-d519-455e-9ae8-033ed6a208d5">

### Ridge Regression (L2 Regularizer)
Ridge Regression is a regularization technique that reduces overfitting in linear regression models. Ridge regression penalizes the loss function due
to this reason we are not able to get 0 in training thus preventing overfitting. By Ridge regression, we find the best parameters with which
we will have loss that will be negligible but the best-fit line won't cause overfitting.

```
clf = Ridge(alpha=1.0)
clf.fit(X, y)
```
alpha in the code above is the penalizer itself in the link below it is seen as Lambda Y

[Ridge Regression Maths](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials/blob/main/2-Ridge%20And%20Lasso%20Regression.pdf)
[Practical Example](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials/blob/main/Ridge%20And%20Lasso%20Practical.ipynb)

### Lasso Regression (L1 Regularizer)
Lasso Regression is a regularization technique. A plus point to lasso over L2 regularizer is that lasso regression also helps in feature selection.

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/480e2a29-2b0f-4955-8751-84923e627d6c">



### SVM classification (Handling non-linearity):

#### Adding polynomial features
This is a method where more features are created from existing features for example from x1 we create x2 by taking the square of x1. **Be aware**: By using this the size of the number of features increases meaning more computation will be required.

```
from sklearn.datasets import make_moons
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import PolynomialFeatures
polynomial_svm_clf = Pipeline((
 ("poly_features", PolynomialFeatures(degree=3)),
 ("scaler", StandardScaler()),
 ("svm_clf", LinearSVC(C=10, loss="hinge"))
 ))
polynomial_svm_clf.fit(X, y)
```

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/36a5219f-7248-4fd6-9a17-005113a2f1c7">

#### Polynomial Kernel

#### Adding Similarity Features
It creates more features

#### Gaussian RBF Kernel
Does the same thing as Adding Similarity Features but better. It uses a kernel trick

```
rbf_kernel_svm_clf = Pipeline((
 ("scaler", StandardScaler()),
 ("svm_clf", SVC(kernel="rbf", gamma=5, C=0.001))
 ))
rbf_kernel_svm_clf.fit(X, y)
```

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/013c57fe-30e4-4e90-aa4c-a36d60fb225a">


<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/9e051583-7c1a-4239-8c97-f17a7472fdde">


### SVM Regression

Unlike the SVM classifier in which we try to create the largest possible street separating the data, in SVM regression we try to fit as many instances in the street as possible.

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/6f10f510-87be-4342-910b-4cbc16eff09c">


For non-linear data, we can use **kernel trick** to manage it.

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/24524ac5-32cd-455e-93f5-2a9965ac2e50">

### Ensemble learning

Ensemble learning is a technique where we train multiple models and get an output according to each model output for example averaging each output. A common example of Ensemble learning can be RandomForests where we train multiple decision trees, similarly training SVM, Linear Regression, and outputting the result according to each model's output is also an ensemble learning technique.

#### Bagging and Pasting

Bagging and pasting is where we train multiple models on a number of rows from a dataset. We take several rows from a dataset and provide them to run the models in groups i.e group1 will be given to model1 while group2 will be given to model2. In **Bagging** there can be repeated rows in multiple datasets while in **Pasting** observations are unique.
Bagging is used when the dataset is large while pasting is used when we have a small dataset. Practically I haven't seen much performance difference,

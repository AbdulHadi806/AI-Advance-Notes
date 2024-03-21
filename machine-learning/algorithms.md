# ML Common Algorithms

[More Advance Notes to refer to](https://github.com/krishnaik06/Machine-Learning-Algorithms-Materials)

## Classifiers

### Multilabel classification

Multilabel classification is the type of classification in which we need to predict more than one class for example an image where you need to predict
people. The image has 2 people and we need to predict there names(data of those people have already been provided) then what the model will do is that it will have to predict 2 classes for example, Ali and Ahmed. Let's say now we want to check if Ali, Ahmed and let's say Sam is in the picture, our model will say [1,1,0] meaning [1=ali, 2=ahmed, 3=sam]

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

# Evaluation Methods

## Classifier Evaluation methods

## Confusion matrix

```
from sklearn.metrics import confusion_matrix
confusion_matrix(y_train_5, y_train_pred)
```

[Confusion Matrix more details](https://github.com/AbdulHadi806/Machine-learning-Basic-notes/blob/main/Machine-learning-Basic-notes/MLMaths/BasicMaths.md#confusion-matric)

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/826e32ae-177d-4ff6-859c-8c735df136fa">

## Precision

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/19014fa9-d9e8-4d89-a655-7d25ad70b3d7">

## Recall

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/1ae0e9fd-2783-45f6-b2df-d1e4cee46384">

## F1 score

It is often convenient to combine the precision and recall into a single metric called the F1 score, in particular if you need a simple way to compare
two classifiers. The F1 score is the harmonic mean of precision and recall, whereas the regular mean treats all values equally, the Aharmonic mean
gives more weight to low values. As a result, the classifier will only get a high F1 score if both recall and precision are high.

```
from sklearn.metrics import f1_score
f1_score(y_train_5, y_pred)
```

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/ba66a76c-083e-481b-a9b4-adc07fa961d7">

## Precision/Recall Tradeoff
Precision/Recall tradeoff means that if we increase Recall then precision will decrease or vice versa, we cannot keep both high. There are use cases
where we need the precision to be high while some areas where we need Recall to be high, in such a case we adjust it according to our needs. For
example in the case of a security system, we would prefer Recall to be high in which we need to predict all shoplifters in such a case 30% precision
will be good and we will get 99% recall meaning all shoplifters will get arrested but yes there will be some false alerts but at least all shoplifters
will get arrested. Similarly, in a video system where we will need to block all bad videos, we will need higher precision meaning videos that are
also good may get blocked but at least we won't be able to see anything bad.

## How can precision and recall be adjusted
Precision and recall can be adjusted by playing with the threshold value. Increasing the threshold increases precision while decreasing the threshold value
increases recall and decreases precision.

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/d1811472-bcd3-4491-b135-becfebff6866">

We can see that precision slope is a little bumpier around 400000 threshold, this is because precision sometimes decreases when the threshold increases.

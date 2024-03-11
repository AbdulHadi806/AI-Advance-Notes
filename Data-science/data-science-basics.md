# Data science basics by beginner for beginners

### What is the purpose of a data scientist?
A data scientist's purpose is to give data insights through finding patterns. We find these insights so that we can apply it such as businesses. A data can be data of weather, stock, and much more.

### Data Science Processes

<img width="400" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/597cb69f-6d64-4536-b71c-c836b8540219">

## Statistical Distribution of Attributes

### Central Tendency: Central tendency refers to the typical or central value around which the data points tend to cluster. There are several measures of central tendency:

**a. Mean**: The arithmetic mean is calculated by summing all the values in a dataset and then dividing by the number of values. It is sensitive to outliers.

**b. Median**: The median is the middle value in a sorted dataset. It is less affected by extreme values (outliers) compared to the mean.

**c. Mode**: The mode is the value that occurs most frequently in the dataset. A dataset can have one mode, more than one mode (multimodal), or no mode at all.

These measures give different insights into the central value of a dataset, and the choice of measure depends on the nature of the data and the analysis objectives.

### Dispersion (Variability): Dispersion, also known as variability, measures the spread or scatter of the data points around the central tendency. Common measures of dispersion include:

**a. Range**: The range is the difference between the maximum and minimum values in the dataset. It provides a simple measure of the spread but is sensitive to outliers.

**b. Variance**: Variance measures the average squared deviation of each data point from the mean. It gives a measure of how much the values in the dataset deviate from the mean.

**c. Standard Deviation**: Standard deviation is the square root of the variance. It provides a measure of the average distance of data points from the mean and is often used as a standard measure of dispersion.

**d. Interquartile Range (IQR)**: The IQR is the difference between the third quartile (Q3) and the first quartile (Q1) in a dataset. It is less sensitive to outliers than the range and provides a measure of the spread of the middle 50% of the data.

### Proximity (Similarity): Proximity refers to the degree of similarity or closeness between data points in a dataset. Proximity measures are often used in clustering and classification tasks to group similar data points together. Common proximity measures include:

**a. Euclidean Distance**: Euclidean distance measures the straight-line distance between two data points in a multidimensional space. It is widely used in various machine learning algorithms, including k-means clustering and k-nearest neighbors.

**b. Cosine Similarity**: Cosine similarity measures the cosine of the angle between two vectors in a multidimensional space. It is commonly used in text analysis and recommendation systems.

**c. Jaccard Similarity**: Jaccard similarity measures the similarity between two sets by comparing the intersection of the sets to their union. It is often used in text analysis and information retrieval tasks.



## Preprocessing

<img width="320" alt="image" src="https://github.com/AbdulHadi806/AI-Advance-Notes/assets/113926529/2dd1e2a1-6ace-45d8-9536-b5f8358da420">

### PCA(principal component analysis)
PCA takes data, finds patterns, it figures out which pattern is more closely related. Once it finds these patterns, PCA creates new components called principal components. These components are combinations of the original attributes. Then PCA checks for similar data and discards the data that is not related, thus it reduces the dimensions of the data.

### Normalization
[Famouse Normalization techniques StandardScaler, Min-Max](https://github.com/AbdulHadi806/Machine-learning-Basic-notes/blob/main/Machine-learning-Basic-notes/MLMaths/BasicMaths.md#scaling-data-evaluating-models-on-data)

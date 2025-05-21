# Scikit-Learn (Sklearn)
Scikit-learn (Sklearn) is the robust library for machine learning in Python. It provides a selection of efficient tools for machine learning and statistical modeling including classification, regression, clustering and dimensionality reduction via a consistence interface in Python.
## Installation:
NumPy and Scipy are prerequisite for installation, followed by

``` pip install -U scikit-learn ```

## Features
1. Supervised Learning algorithms − Linear Regression, Support Vector Machine (SVM), Decision Tree etc., are the part of scikit-learn.
2. Unsupervised Learning algorithms − Clustering, factor analysis, PCA (Principal Component Analysis) to unsupervised neural networks.
3. Clustering − Grouping unlabeled data.
4. Cross Validation − To check the accuracy of supervised models on unseen data.
5. Dimensionality Reduction − Reducing the number of attributes in data which can be further used for summarisation, visualisation and feature selection.
6. Ensemble methods − Combining the predictions of multiple supervised models.
7. Feature extraction − To extract the features from data to define the attributes in image and text data.
8. Feature selection − Identify useful attributes to create supervised models.
9. An Open Source Library

## Modelling Process
### Dataset Loading:
A collection of data is called dataset. It is having the following two components − Features and Response
1. Features - The variables of data are called its features. They are also known as predictors, inputs or attributes.
  a) Feature matrix − It is the collection of features, in case there are more than one.
  b) Feature Names − It is the list of all the names of the features.
2. Response - It is the output variable that basically depends upon the feature variables. They are also known as target, label or output.
   a) Response Vector − It is used to represent response column. 
   b) Target Names − It represent the possible values taken by a response vector.

Scikit-learn contains datasets like iris and digits for classification and the Boston house prices for regression which are in-built.
Example:
```
from sklearn.datasets import load_iris
iris = load_iris()
#iris dataset contains measurement of different types of iris flower
X = iris.data
y = iris.target
feature_names = iris.feature_names #contains input data
target_names = iris.target_names #contains target values
print("Feature names:", feature_names)
print("Target names:", target_names)
print("\nFirst 10 rows of X:\n", X[:10])
```
Output: 
```
Feature names: ['sepal length (cm)', 'sepal width (cm)', 'petal length (cm)', 'petal width (cm)']
Target names: ['setosa' 'versicolor' 'virginica']

First 10 rows of X:
 [[5.1 3.5 1.4 0.2]
 [4.9 3.  1.4 0.2]
 [4.7 3.2 1.3 0.2]
 [4.6 3.1 1.5 0.2]
 [5.  3.6 1.4 0.2]
 [5.4 3.9 1.7 0.4]
 [4.6 3.4 1.4 0.3]
 [5.  3.4 1.5 0.2]
 [4.4 2.9 1.4 0.2]
 [4.9 3.1 1.5 0.1]]

```

### Splitting the dataset
This step is important to check the accuracy of the model. It is split into 2 peices i.e, training set and testing set.
1. Training Set - To train the model
2. Testing Set - To test the model

Example:
The following example will split the data into 70:30 ratio, i.e. 70% data will be used as training data and 30% will be used as testing data. 

```
from sklearn.datasets import load_iris
iris = load_iris()
X = iris.data
y = iris.target

from sklearn.model_selection import train_test_split #splits the dataset
X_train, X_test, y_train, y_test = train_test_split(
   X, y, test_size = 0.3, random_state = 1
)
# x - Feature matrix, y - response vector, test_size - size of testing set, random state = 1 - Guarantee that the split will always be the same
print(X_train.shape)
print(X_test.shape)
print(y_train.shape)
print(y_test.shape)
```

Output:
```
(105, 4)
(45, 4)
(105,)
(45,)
```
### Train the Model
 This dataset can be used to train some prediction-model.
 Example:

  ```
from sklearn.datasets import load_iris
iris = load_iris()
X = iris.data
y = iris.target
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(
   X, y, test_size = 0.4, random_state=1
)
from sklearn.neighbors import KNeighborsClassifier
from sklearn import metrics
classifier_knn = KNeighborsClassifier(n_neighbors = 3)
classifier_knn.fit(X_train, y_train)
y_pred = classifier_knn.predict(X_test)
# Finding accuracy by comparing actual response values(y_test)with predicted response value(y_pred)
print("Accuracy:", metrics.accuracy_score(y_test, y_pred))
# Providing sample data and the model will make prediction out of that data

sample = [[5, 5, 3, 2], [2, 4, 3, 5]]
preds = classifier_knn.predict(sample)
pred_species = [iris.target_names[p] for p in preds] print("Predictions:", pred_species)
  ```



















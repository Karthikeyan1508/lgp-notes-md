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
Output:
```
Accuracy: 0.9833333333333333
Predictions: ['versicolor', 'virginica']
```

## Model Persistence
Once the model is trained, it should be persist for future use so that we do not need to retrain it again and again. It can be done with the help of dump and load features of joblib package.

Consider the example below in which we will be saving the above trained model (classifier_knn) for future use −
```
from sklearn.externals import joblib
joblib.dump(classifier_knn, 'iris_classifier_knn.joblib')
```
The above code will save the model into file named iris_classifier_knn.joblib. Now, the object can be reloaded from the file with the help of following code −
```
joblib.load('iris_classifier_knn.joblib')
```

## Preprocessing the Data
Before inputting that data to machine learning algorithms, we need to convert it into meaningful data. This process is called preprocessing the data. 

**1. Binarisation**
To convert numerical values into Boolean values.
Example:
```
import numpy as np
from sklearn import preprocessing

# Correcting input data array
input_data = np.array([
   [2.1, -1.9, 5.5],
   [-1.5, 2.4, 3.5],
   [0.5, -7.9, 5.6], 
   [5.9, 2.3, -5.8]
])

# Apply binarization
data_binarized = preprocessing.Binarizer(threshold=0.5).transform(input_data)

print("\nBinarized data:\n", data_binarized)
```
Output:
```
Binarized data:
 [[1. 0. 1.]
 [0. 1. 1.]
 [0. 0. 1.]
 [1. 1. 0.]]
```
In the above example, we used threshold value = 0.5 and that is why, all the values above 0.5 would be converted to 1, and all the values below 0.5 would be converted to 0.

**2. Mean Removal**
To eliminate the mean from feature vector so that every feature centered on zero.
Example:
```
import numpy as np
from sklearn import preprocessing
Input_data = np.array([
   [2.1, -1.9, 5.5],
   [-1.5, 2.4, 3.5],
   [0.5, -7.9, 5.6],
   [5.9, 2.3, -5.8]]
)
#displaying the mean and the standard deviation of the input data
print("Mean =", input_data.mean(axis=0))
print("Stddeviation = ", input_data.std(axis=0))
#Removing the mean and the standard deviation of the input data
data_scaled = preprocessing.scale(input_data)
print("Mean_removed =", data_scaled.mean(axis=0))
print("Stddeviation_removed =", data_scaled.std(axis=0))
```

Output:
```
Mean = [ 1.75  -1.275  2.2  ]
Stddeviation =  [2.71431391 4.20022321 4.69414529]
Mean_removed = [1.11022302e-16 0.00000000e+00 0.00000000e+00]
Stddeviation_removed = [1. 1. 1.]
```

**3. Scaling**

To normalize the range of independent features in your data before feeding it to a machine learning model so that no feature dominates because of its scale.
Example:

```
import numpy as np
from sklearn import preprocessing
Input_data = np.array(
   [
      [2.1, -1.9, 5.5],
      [-1.5, 2.4, 3.5],
      [0.5, -7.9, 5.6],
      [5.9, 2.3, -5.8]
   ]
)
data_scaler_minmax = preprocessing.MinMaxScaler(feature_range=(0,1))
data_scaled_minmax = data_scaler_minmax.fit_transform(input_data)
print ("\nMin max scaled data:\n", data_scaled_minmax)
```
Output:
```
Min max scaled data:
 [[0.48648649 0.58252427 0.99122807]
 [0.         1.         0.81578947]
 [0.27027027 0.         1.        ]
 [1.         0.99029126 0.        ]]
```

**4. Normalisation**
Normalisation of feature vectors is necessary so that the feature vectors can be measured at common scale. There are two types of normalisation
1. L1 Normalisation:
    It is called Least Absolute Deviations. It modifies the value in such a manner that the sum of the absolute values remains always up to 1 in each row.
L1 normalization scales each row (sample) so that the sum of the absolute values in that row equals 1.

![image](https://github.com/user-attachments/assets/4388d90e-23fe-4828-9f35-385f647c3e52)


   Example:
   ```
import numpy as np
from sklearn import preprocessing
Input_data = np.array(
   [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
   ]
)
data_normalized_l1 = preprocessing.normalize(input_data, norm='l1')
print("\nL1 normalized data:\n", data_normalized_l1)
   ```
Output:
```
L1 normalized data:
 [[0.16666667 0.33333333 0.5       ]
  [0.26666667 0.33333333 0.4       ]
  [0.29166667 0.33333333 0.375     ]]
```

2. L2 Normalisation
It is  called Least Squares normalisation. It modifies the value in such a manner that the sum of the squares remains always up to 1 in each row.
L2 normalization scales each row (sample) so that the sum of the squares of the elements in the row equals 1.

![image](https://github.com/user-attachments/assets/ab107d15-916f-4ac9-8439-f4a4ec3c4f74)

Example
```
import numpy as np
from sklearn import preprocessing
Input_data = np.array(
   [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
   ]
)
data_normalized_l2 = preprocessing.normalize(input_data, norm='l2')
print("\nL1 normalized data:\n", data_normalized_l2)
```

Output:
```
L2 normalized data:
 [[0.26726124 0.53452248 0.80178373]
  [0.45584231 0.56980288 0.68376346]
  [0.50257071 0.57436653 0.64616234]]

```

## Downloading the dataset
we can download iris dataset in the form of a Pandas DataFrame with the help of python seaborn library.
```
import seaborn as sns
iris = sns.load_dataset('iris')
iris.head()
```
Output:
![image](https://github.com/user-attachments/assets/ec42fcc4-db47-44c0-82f4-edd23d4dacce)

# Estimator API
It provides a consistent interface for a wide range of ML applications thats why all machine learning algorithms in Scikit-Learn are implemented via Estimator API. The object that learns from the data (fitting the data) is an estimator. It can be used with any of the algorithms like classification, regression, clustering or even with a transformer, that extracts useful features from raw data.

For fitting the data, all estimator objects expose a fit method that takes a dataset shown as follows:
Without parameter: ``` estimator.fit(data) ```
With parameter: ``` estimator = Estimator (param1=1, param2=2)
                    estimator.param1
                    ```
## Uses of Estimator API:
1) .fit() trains the model on the input data.
2) .predict() makes predictions using the trained model.
3) .score() evaluates the model’s performance.
4) .transform() applies data transformations (e.g., scaling, encoding).
5) .fit_transform() combines fitting and transforming in one step.

## Steps in using Estimator API

Step 1: Choose a class of model
It can be done by importing the appropriate Estimator class from Scikit-learn.

Step 2: Choose model hyperparameters
It can be done by instantiating the class with desired values.

Step 3: Arranging the data
We need to arrange the data into features matrix (X) and target vector(y).

Step 4: Model Fitting
It can be done by calling fit() method of the model instance.

Step 5: Applying the model
After fitting the model, we can apply it to new data. For supervised learning, use predict() method to predict the labels for unknown data. While for unsupervised learning, use predict() or transform() to infer properties of the data.


## KNN Algorithm
The k-nearest neighbors (KNN) algorithm is a non-parametric, supervised learning classifier, which uses proximity to make classifications or predictions about the grouping of an individual data point. 

For classification problems, a class label is assigned on the basis of a majority vote—i.e. the label that is most frequently represented around a given data point is used. While this is technically considered “plurality voting”, the term, “majority vote” is more commonly used in literature. The distinction between these terminologies is that “majority voting” technically requires a majority of greater than 50%, which primarily works when there are only two categories. When you have multiple classes—e.g. four categories, you don’t necessarily need 50% of the vote to make a conclusion about a class; you could assign a class label with a vote of greater than 25%.






















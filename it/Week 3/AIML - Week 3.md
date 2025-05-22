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

![image](https://github.com/user-attachments/assets/9c59104e-641b-4467-9bc1-8f8435489d5f)

Regression problems use a similar concept as classification problem, but in this case, the average the k nearest neighbors is taken to make a prediction about a classification. The main distinction here is that classification is used for discrete values, whereas regression is used with continuous ones. However, before a classification can be made, the distance must be defined. Euclidean distance is most commonly used.

### Compute KNN:

The k value in the k-NN algorithm defines how many neighbors will be checked to determine the classification of a specific query point. For example, if k=1, the instance will be assigned to the same class as its single nearest neighbor.

Lower values of k can have high variance, but low bias, and larger values of k may lead to high bias and lower variance. The choice of k will largely depend on the input data as data with more outliers or noise will likely perform better with higher values of k. Overall, it is recommended to have an odd number for k to avoid ties in classification, and cross-validation tactics can help you choose the optimal k for your dataset.

```
from sklearn.pipeline import Pipeline
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.datasets import load_iris
import pandas as pd

# Load iris dataset
iris = load_iris()
X = pd.DataFrame(iris.data, columns=iris.feature_names)
y = iris.target

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Identify numerical columns (all in iris)
numerical_features = X.columns

# Create preprocessor
preprocessorForFeatures = ColumnTransformer(
    transformers=[
        ('num', StandardScaler(), numerical_features)
    ]
)

# KNN classifier
knnClassifier = KNeighborsClassifier(n_neighbors=5, metric='minkowski', p=2)

# Build pipeline
knn_model = Pipeline(steps=[
    ('preprocessor', preprocessorForFeatures),
    ('classifier', knnClassifier)
])

# Train the model
knn_model.fit(X_train, y_train)

# Predict
y_pred = knn_model.predict(X_test)
print("Predictions:", y_pred)

```

Output:
Predictions: [1 0 2 1 1 0 1 2 1 1 2 0 0 0 0 1 2 1 1 2 0 2 0 2 2 2 2 2 0 0 0 0 1 0 0 2 1
 0 0 0 2 1 1 0 0]

 
## Applications of k-NN in machine learning

1. Data preprocessing: Datasets frequently have missing values, but the KNN algorithm can estimate for those values in a process known as missing data imputation.

2. Recommendation Engines: Using clickstream data from websites, the KNN algorithm has been used to provide automatic recommendations to users on additional content.

3. Finance: It has also been used in a variety of finance and economic use cases especially in stock market forecasting

4. Healthcare: KNN has also had application within the healthcare industry, making predictions on the risk of heart attacks and prostate cancer.

5. Pattern Recognition: KNN has also assisted in identifying patterns, such as in text and digit classification. This has been particularly helpful in identifying handwritten numbers that you might find on forms or mailing envelopes.

## Advantages of KNN Algorithm:

1. Easy to implement: Given the algorithm’s simplicity and accuracy, it is one of the first classifiers that a new data scientist will learn.

2. Adapts easily: As new training samples are added, the algorithm adjusts to account for any new data since all training data is stored into memory.

3. Few hyperparameters: KNN only requires a k value and a distance metric, which is low when compared to other machine learning algorithms.

## Disadvantages of KNN Algorithm:

Does not scale well: Since KNN is a lazy algorithm, it takes up more memory and data storage compared to other classifiers. This can be costly from both a time and money perspective. More memory and storage will drive up business expenses and more data can take longer to compute. While different data structures, such as Ball-Tree, have been created to address the computational inefficiencies, a different classifier may be ideal depending on the business problem.

Curse of dimensionality: The KNN algorithm tends to fall victim to the curse of dimensionality, which means that it doesn’t perform well with high-dimensional data inputs. This is sometimes also referred to as the peaking phenomenon, where after the algorithm attains the optimal number of features, additional features increases the amount of classification errors, especially when the sample size is smaller.

Prone to overfitting: Due to the “curse of dimensionality”, KNN is also more prone to overfitting. While feature selection and dimensionality reduction techniques are leveraged to prevent this from occurring, the value of k can also impact the model’s behavior. Lower values of k can overfit the data, whereas higher values of k tend to “smooth out” the prediction values since it is averaging the values over a greater area, or neighborhood. However, if the value of k is too high, then it can underfit the data.

## Naïve Bayes classifiers
The Naïve Bayes classifier is a supervised machine learning algorithm that is used for classification tasks such as text classification. They use principles of probability to perform classification tasks. Naïve Bayes is also known as a probabilistic classifier since it is based on Bayes’ Theorem. conditional probabilities represent the probability of an event given some other event has occurred, which is represented with the following formula:

![image](https://github.com/user-attachments/assets/5a9e9908-2acf-4aa7-86cd-968db5587899)

The prior probability is the initial probability of an event before it is contextualized under a certain condition, or the marginal probability. The posterior probability is the probability of an event after observing a piece of data.

It assumes that predictors in a Naïve Bayes model are conditionally independent, or unrelated to any of the other feature in the model. It also assumes that all features contribute equally to the outcome. While these assumptions are often violated in real-world scenarios (e.g. a subsequent word in an e-mail is dependent upon the word that precedes it), it simplifies a classification problem by making it more computationally tractable. That is, only a single probability will now be required for each variable, which, in turn, makes the model computation easier. Despite this unrealistic independence assumption, the classification algorithm performs well, particularly with small sample sizes.

it’ll use conditional and prior probabilities to calculate the posterior probabilities using the following formula:


![image](https://github.com/user-attachments/assets/9b9bdb43-1fe5-4cc2-b488-6b0098714715)

Let’s imagine text classification use case to illustrate how the Naïve Bayes algorithm works. Picture an e-mail provider that is looking to improve their spam filter. The training data would consist of words from e-mails that have been classified as either “spam” or “not spam”. From there, the class conditional probabilities and the prior probabilities are calculated to yield the posterior probability. The Naïve Bayes classifier will operate by returning the class, which has the maximum posterior probability out of a group of classes (i.e. “spam” or “not spam”) for a given e-mail. The class-conditional probabilities are the individual likelihoods of each word in an e-mail. These are calculated by determining the frequency of each word for each category—i.e. “spam” or “not spam”, which is also known as the maximum likelihood estimation (MLE). In this example, if we were examining if the phrase, “Dear Sir”, we’d just calculate how often those words occur within all spam and non-spam e-mails. This can be represented by the formula below, where y is “Dear Sir” and x is “spam”.


![image](https://github.com/user-attachments/assets/bae4527c-f79e-4cc9-ab8b-8f6d008b624a)


### Evaluating Naïve Bayes classifier

To evaluate your classifier is to plot a confusion matrix, which will plot the actual and predicted values within a matrix. Rows generally represent the actual values while columns represent the predicted values. 


![image](https://github.com/user-attachments/assets/e621689f-282b-476e-909f-75a144c9faee)

However, if you were predicting images from zero through 9, you’d have a 10 x 10 plot. If you wanted to know the number of times that classifier “confused” images of 4s with 9s, you’d only need to check the 4th row and the 9th column.



![image](https://github.com/user-attachments/assets/c1d134ba-36d2-4587-b107-028c60d3ed23)


## Types of Naïve Bayes classifiers

1. Gaussian Naïve Bayes (GaussianNB): This is a variant of the Naïve Bayes classifier, which is used with Gaussian distributions—i.e. normal distributions—and continuous variables. This model is fitted by finding the mean and standard deviation of each class.
2. Multinomial Naïve Bayes (MultinomialNB): This type of Naïve Bayes classifier assumes that the features are from multinomial distributions. This variant is useful when using discrete data, such as frequency counts, and it is typically applied within natural language processing use cases, like spam classification.
3. Bernoulli Naïve Bayes (BernoulliNB): This is another variant of the Naïve Bayes classifier, which is used with Boolean variables—that is, variables with two values, such as True and False or 1 and 0.


### Applications of the Naïve Bayes classifier

1. Spam filtering: Spam classification is one of the most popular applications of Naïve Bayes cited in literature.
2. Document classification: Document and text classification go hand in hand. Another popular use case of Naïve Bayes is content classification. Imagine the content categories of a News media website. All the content categories can be classified under a topic taxonomy based on the each article on the site. Federick Mosteller and David Wallace are credited with the first application of Bayesian inference within their 1963 paper (link resides outside ibm.com).
3. Sentiment analysis: While this is another form of text classification, sentiment analysis is commonly leveraged within marketing to better understand and quantify opinions and attitudes around specific products and brands. 
4. Mental state predictions: Using fMRI data, naïve bayes has been leveraged to predict different cognitive states among humans. T

### Advantages
1. Less complex: Compared to other classifiers, Naïve Bayes is considered a simpler classifier since the parameters are easier to estimate. As a result, it’s one of the first algorithms learned within data science and machine learning courses.
2. Scales well: Compared to logistic regression, Naïve Bayes is considered a fast and efficient classifier that is fairly accurate when the conditional independence assumption holds. It also has low storage requirements.
3. Can handle high-dimensional data: Use cases, such document classification, can have a high number of dimensions, which can be difficult for other classifiers to manage.

Disadvantages:
1. Subject to Zero frequency: Zero frequency occurs when a categorical variable does not exist within the training set. For example, imagine that we’re trying to find the maximum likelihood estimator for the word, “sir” given class “spam”, but the word, “sir” doesn’t exist in the training data. The probability in this case would zero, and since this classifier multiplies all the conditional probabilities together, this also means that posterior probability will be zero. To avoid this issue, laplace smoothing can be leveraged.
2. Unrealistic core assumption: While the conditional independence assumption overall performs well, the assumption does not always hold, leading to incorrect classifications.











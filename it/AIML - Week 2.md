# Python - Matplotlib
Matplotlib is a powerful and versatile open-source plotting library for Python, designed to help users visualize data in a variety of formats. It is designed to work with NumPy arrays and pandas dataframes. The library makes it easy to make graphs from tabular data. 

## Matplotlib Pyplot
Pyplot is a Matplotlib module that provides simple functions for adding plot elements, such as lines, images, text, etc. to the axes in the current figure.
## Installation:
```pip install matplotlib```

### Steps to Use Pyplot:
  1. **Import Matplotlib:** Start by importing matplotlib.pyplot as plt.
  2. **Create Data:** Prepare your data in the form of lists or arrays.
  3. **Plot Data:** Use plt.plot() to create the plot.
  4. **Customize Plot:** Add titles, labels, and other elements using methods like plt.title(), plt.xlabel(), and plt.ylabel().
  5. **Display Plot:** Use plt.show() to display the plot.

**Syntax:** matplotlib.pyplot.plot()

## Parts of Matplotlib
**Figure:** Whole area chosen for plotting
``` 
fig = plt.figure()
plt.show()
```
**Axes:** Area where data is plotted and it can be added by using methods add_subplot(nrows, ncols, index) return axes object
```
fig = plt.figure()
ax = fig.add_subplot()
plt.show()
```
**Figure size:** Adjusting Figure Size => plt.figure(figsize=(x, y))
```
fig = plt.figure(figsize=(3, 3))
ax = fig.add_subplot(1, 1, 1)
plt.show()
```
## Create titles and axis label as method
```
fig = plt.figure(figsize=(3,3))
ax = fig.add_subplot(111)
ax.set_title("Figure")
ax.set_xlabel("X-Axis")
ax.set_ylabel('Y-Axis')
ax.set_xlim([0,5])
ax.set_ylim([0,10])
plt.show()
```
![image](https://github.com/user-attachments/assets/d7b9f911-6599-4e5c-a787-8d3dcf3f73ff)

## Create Multiple Subplots
```
import matplotlib.pyplot as plt
x=[1, 2, 3, 4]
y=[1, 2, 3, 4]
plt.plot(x,y)
plt.show()
```
![image](https://github.com/user-attachments/assets/fc31454f-c588-4c09-84e3-98463820c95e)

## Create legends
A matplotlib legend is a small box that describes the various elements of the plot in terms of lines and markers that have distinct styles or colors.

**Attributes:**

1. shadow: [None or bool] Whether to draw a shadow behind the legend.It’s Default value is None.
2. markerscale: [None or int or float] The relative size of legend markers compared with the originally drawn ones.The Default is None.
3. numpoints: [None or int] The number of marker points in the legend when creating a legend entry for a Line2D (line).The Default is None.
4. fontsize: The font size of the legend.If the value is numeric the size will be the absolute font size in points.
5. facecolor: [None or “inherit” or color] The legend’s background color.
6. edgecolor: [None or “inherit” or color] The legend’s background patch edge color.

```
#adding legend in graph => plt.legend(x, y, label='legend'); plt.legend() will use
x = list(range(0,5))
y = list(range(0,10, 2))

fig = plt.figure(figsize=(3,3))
ax = fig.add_subplot(1,1,1)
ax.set(title="Figure"
      , xlabel='x-asix'
      , ylabel='y-axis'
      , xlim=(0,5)
      , ylim=(0,10))
plt.plot(x,y, label='legend')
plt.legend()
plt.show()
```
## Line Plot
Line Plot is used to visualize a trend in data and is also used to compare two variables.
**Syntax:** ``` plt.plot(x,y) ```
```
x = [1, 5, 8, 12, 15, 19, 22, 26, 29]
y = [29.3, 30.1, 30.4, 31.5, 32.3, 32.6, 31.8, 32.4, 32.7]

fig = plt.figure(figsize=(8,6))
ax = fig.add_subplot(1,1,1)
ax.set(title='Line Plot Graph'
       , xlabel='X-Axis'
       , ylabel='Y-Axis'
       , xlim=(0, 30)
       , ylim=(25, 35))
ax.plot(x, y)
plt.show()
```
![image](https://github.com/user-attachments/assets/bc87168c-fbe0-42e8-9173-eee84f15cf81)
### Parameter for Plot
1. **color** - Sets the color of the line.
2. **linestyle** - Sets the line style, e.g., solid, dashed, etc.
3. **linewidth** - Sets the thickness of a line.
4. **marker** - Chooses a marker for data points, e.g., circle, triangle, etc.
5. **markersize** - Sets the size of the chosen marker.
6. **label** - Names the line, which will come in legend.

```
fig = plt.figure(figsize=(6,3))
ax = fig.add_subplot(1,1,1)
ax.set(title='Line Plot Graph'
       , xlabel='X-Axis'
       , ylabel='Y-Axis'
       , xlim=(0, 30)
       , ylim=(25, 35))
ax.plot(x
        , y
        , color='black'
        , linestyle='dotted'
        , linewidth=1
        , marker='o'
        , markersize=10
        , label='label')
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/fb286ab6-f046-43aa-bdd5-f6ff4f98416f)

## Scatter Graph
It similar to a line graph which is used to show how one variable is related to another. It consists of data points, if it is linear then it is highly correlated and only marks the data point.
**Syntax:** ``` plt.scatter(x,y) ```
### Parameter of Scatter Graph
1. **c:** Sets color of markers.
2. **s:** Sets the size of markers.
3. **marker:** Select a marker. e.g.: circle, triangle, etc
4. **edgecolor:** Sets the color of lines on the edges of markers.
```
x=[1,4,6,4,2]
y=[10,10,1,5,0]

fig = plt.figure(figsize=(8,4))
ax = fig.add_subplot()
ax.scatter(x
           , y
           , c='blue'
           , s=500
           , marker='o'
           , edgecolor='black'
           , label='Scatter')
ax.set_title('Scatter Graph')
ax.set_xlabel('X-Axis')
ax.set_ylabel('Y-Axis')
plt.legend()
```
![image](https://github.com/user-attachments/assets/1402637a-a02f-4918-ae66-1be19a7f71c1)

## Bar Chart
It is mostly used to compare categories, for vertical bar plots and horizontal bar plots.
**Syntax:** ``` bar(x, height) or bar(y,width) ```

### Parameter of Bar Graph
1. **Color:** Sets the color of bars.
2. **edgecolor:** Sets the color of the borderline of bars.
3. **label:** Sets label to a bar, appearing in legend.
4. **color:** The color of the bar.
5. **align:** Aligns the bars with respect to x-coordinates.

```
# vertical bar graph
import matplotlib.pyplot as plt 

x = [1, 2, 3]
y = [10,20,30]

fig = plt.figure(figsize=(8,4))
ax = fig.add_subplot()

ax.set(title='Bar Graph'
       , xlabel='X-Axis'
       , ylabel='Y-Axis'
       , xticks=x
       , label='label'
       , xticklabels=['first', 'second', 'third'])
ax.bar(x
       , y
       , color='Blue'
       , edgecolor='Black'
       , width=0.5
       , align='edge'
       , label='label'
       , linewidth=3)

plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/1bad5135-6626-4730-9121-f2fedffebb82)

```
#horizontal bar graph
import matplotlib.pyplot as plt 

x = [1, 2, 3]
y = [10,20,30]

fig = plt.figure(figsize=(8,4))
ax = fig.add_subplot()

ax.set(title='Bar Graph'
       , xlabel='X-Axis'
       , ylabel='Y-Axis'
       , xticks=x
       , label='label'
       , xticklabels=['first', 'second', 'third'])
plt.barh(x
       , y
       , color='blue'
       , edgecolor='black'
       , height=0.5
       , align='edge'
       , label='label')

plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/f1421e86-8074-4bb4-82f7-313c940049b3)

## Pie Plot
It is effective in showing the proportion of categories and is best suited for comparing fewer categories. It is used to highlight the proportion of one or a group of categories.
Syntax: pie(x), x: size of portions, passed as fraction or number

### Parameter of Pie
1. **colors:** Sets the colors of portions.
2. **labels:** Sets the labels of portions.
3. **startangle:** Sets the start angle at which the portion drawing starts.
4. **autopct:** Sets the percentage display format of an area, covering portions.

```
import matplotlib.pyplot as plt 

x=[1,2,3,4,5]

fig=plt.figure(figsize=(4,4))
ax=fig.add_subplot()
ax.set(title='Pie')

plt.pie(x
       , colors=['brown', 'red', 'green', 'yellow', 'blue']
       , labels=['first', 'second', 'third', 'fourth', 'fifth']
       , startangle=0
       , autopct='%1.1f%%')
```
![image](https://github.com/user-attachments/assets/e8c33668-de28-4c9f-956c-92384e9fedea)

## Histogram Chart
It is used to visualize the spread of data in a distribution
Syntax: hist(x), x is the data values

### Parameter of Histogram
1. **Color:** Sets the color of bars.
2. **bins:** Sets the number of bins to be used.
3. **density:** Sets to True where bins display fraction and not the count.

```
import matplotlib.pyplot as plt 

x=[1,2,3,4,5]
fig=plt.figure(figsize=(10,4))
ax=fig.add_subplot()

ax.set(title='Histogram'
      , xlabel='X-Axis'
      , ylabel='Y-Axis')

ax.hist(x
       , color='blue'
       , bins=10
       , density=True
       , orientation='vertical')
```
![image](https://github.com/user-attachments/assets/da22d717-116c-4808-9adb-5205705626da)

## 3-Dimensional Line Graph
```
import numpy as np
import matplotlib.pyplot as plt

fig = plt.figure()
ax = plt.axes(projection='3d')
```
![image](https://github.com/user-attachments/assets/84979c71-97f0-4ac7-8016-92cdb5f29591)

```
# importing mplot3d toolkits
from mpl_toolkits import mplot3d
import numpy as np
import matplotlib.pyplot as plt

fig = plt.figure()

# syntax for 3-D projection
ax = plt.axes(projection ='3d')

# defining axes
z = np.linspace(0, 1, 100)
x = z * np.sin(25 * z)
y = z * np.cos(25 * z)
c = x + y
ax.scatter(x, y, z, c = c)

# syntax for plotting
ax.set_title('3d Scatter plot geeks for geeks')
plt.show()
```
![image](https://github.com/user-attachments/assets/0f8aecef-6a5e-4f7e-9718-2b231a52e8a2)

## Working with Images using Matplotlib
The image module in matplotlib library is used for working with images in Python. 
The image module also includes two useful methods
-> imread which is used to read images
-> imshow which is used to display the image. 

```
# importing required libraries
import matplotlib.pyplot as plt
import matplotlib.image as img

# reading the image
testImage = img.imread(r'/content/image.jpg')

# displaying the image
plt.imshow(testImage)
```
![image](https://github.com/user-attachments/assets/578d4d0a-f78d-40f0-b57e-b12f2c870dd3)

### Display an Image in Grayscale in Matplotlib

Open the image using PIL image method and convert it to L mode.L mode image is a single-channel image - normally interpreted as grayscale.

```
from PIL import Image  # Required for opening the image
import matplotlib.pyplot as plt  # Required for displaying the image

# storing image path
fname = r'/content/image.jpg'

# opening image using PIL and converting to grayscale
image = Image.open(fname).convert("L")

# displaying the grayscale image
plt.imshow(image, cmap='gray')
plt.axis('off')  # optional: hides axis ticks
plt.show()
```

![image](https://github.com/user-attachments/assets/c2dab39b-a0af-4d0b-874d-cb72c7de4f8c)

### Display an OpenCV image in Python with Matplotlib
The OpenCV module is an open-source computer vision and machine learning software library. It is a huge open-source library for computer vision, machine learning, and image processing.
OpenCV images with Matplotlib module for that you just need to convert colored image into a gray scale image.

```
# import required modules
import cv2
import matplotlib.pyplot as plt

# read the image
image = cv2.imread(r'/content/image.jpg')

# convert color image into grayscale image
img1 = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)

# plot that grayscale image with Matplotlib
# cmap stands for colormap
plt.imshow(img1, cmap='gray')

# display that image
plt.show()
```

![image](https://github.com/user-attachments/assets/37806df9-4eda-42f0-89bd-61d5324ffe2b)

## Calculate the area of an image using Matplotlib
Algorithm: 
Import the matplotlib.pyplot module.
Import an image using the imread() method.
Use the shape attribute of the image to get the height and width of the image. It fetches the number of channels in the image.
Calculate the area
Display the area.

```
# import necessary library
import matplotlib.pyplot as plt

# read an image
img = plt.imread(r"/content/image.jpg")

# fetch the height and width
height, width, _ = img.shape

# area is calculated as “height x width”
area = height * width

# display the area
print("Area of the image is : ", area)
```
Output -
Area of the image is :  50304


# Math for Machine Learning

## Regression Analysis
Regression analysis is a statistical method for understanding relationships between variables. It is crucial for predictive modeling and interpreting patterns in data. Techniques like linear regression provide the foundation for supervised learning, where the goal is to predict continuous outcomes.

## Linear Regression
Linear regression is a type of supervised machine-learning algorithm that learns from the labelled datasets and maps the data points with most optimized linear functions which can be used for prediction on new datasets. It assumes that there is a linear relationship between the input and output, meaning the output changes at a constant rate as the input changes.
Example: Predicting a person's salary based on the years of experience.

Formula: ![image](https://github.com/user-attachments/assets/94f454c1-621b-4443-81af-50913a462dff)

where x = input variable
y = Predicted value of the dependant variable (output)

### Best Fit Line in Linear Regression
The best-fit line will be the one that optimizes the values of m (slope) and b (intercept)
Equation: ``` y = mx+c ```
Where:
y = the predicted value (dependent variable)
x = the input (independent variable)
m = the slope of the line (how much y changes when x changes)
b = the intercept (the value of y when x = 0)

### The Least Squared Method
It is used to minimize the error between the actual values (data points) and the predicted values from the line.

![image](https://github.com/user-attachments/assets/dc74beec-9e37-4613-8f44-7292fc807c0d)

where, yᵢ is the actual observed value,
yᵢ^​ is the predicted value from the line for the xᵢ


### Evaluation Metrics for Linear Regression
It is used to determine the strength of any linear regression model.
1. **Mean Square Error (MSE):**
Calculates the average of the squared differences between the actual and predicted values for all the data points.

![image](https://github.com/user-attachments/assets/56bdfdda-e670-456d-a373-f6b200faca6c)

where n = the number of data points,
yᵢ = the actual or observed value for the ith data point,
yᵢ^ = the predicted value for the ith data point.

3. **Mean Absolute Error (MAE):**
It calculates the accuracy of a regression model. Lower MAE value indicates better model performance.

![image](https://github.com/user-attachments/assets/a20f4b36-bf25-41c9-9366-50f6c902745a)

where, n = the number of observations
Yi = the actual values.
Yᵢ^ = the predicted values

4. **Root Mean Squared Error (RMSE):**
It describes the model's absolute fit to the data.

![image](https://github.com/user-attachments/assets/f3191aab-5dd2-4bfb-b8b7-5309b887122a)

## Logistic Regression
Logistic regression is a supervised machine learning algorithm used for classification tasks where the goal is to predict the probability that an instance belongs to a given class or not. It transforms the linear regression function continuous value output into categorical value output using a sigmoid function.

Consider X to be independent input - ![image](https://github.com/user-attachments/assets/921be30d-43af-423f-97f3-cff719edf2a3)

the dependent variable is Y having only binary value i.e. 0 or 1 - ![image](https://github.com/user-attachments/assets/a4a17856-a41c-436a-ab68-846354b15005)

Hence the multilinear function will be - ![image](https://github.com/user-attachments/assets/f7bbccde-ed2f-47fc-ac3f-5afc3feb93e4)

where, xᵢ = ith observation of x
wᵢ = weights or Coefficient
b = bias also known as intercept.

Sigmoid Function - ![image](https://github.com/user-attachments/assets/44087b64-4444-4aed-b004-061a8c5b4b66)

where input will be z and we find the probability between 0 and 1. i.e. predicted y.

![image](https://github.com/user-attachments/assets/a96389a5-5b55-4e82-ae84-238874ce8812)

where the probability of being a class can be measured as:
P(y=1)=σ(z)
P(y=0)=1−σ(z)

**Equation of Logistic Regression:**
The final logistic regression equation will be:

![image](https://github.com/user-attachments/assets/64fcdfa1-0e89-4ea5-bd1b-ce4ebba9516f)

## Bayesian Linear Regression
Bayesian regression is used to estimate the parameters of a linear model, incorporating both observed data and prior beliefs about the parameters.
**Bayes’ Theorem**
Bayes’ theorem describes how prior knowledge is updated with new data.

![image](https://github.com/user-attachments/assets/3c8dba56-abf8-488b-9fb4-4281177ebd9a)

where:
P(A|B) is the posterior probability after observing data.
P(B|A) is the likelihood of the data given the parameters.
P(A) is the prior probability.
P(B) is the marginal probability of the observed data.

**Bayesian Regression Formulation**

For a dataset with n samples, the linear relationship is: 

![image](https://github.com/user-attachments/assets/a40c9abf-8372-4ab0-a572-4ab75a7f70d7)

**Conditional Probability Density Function (PDF)**
The probability density function of Y given X is:

![image](https://github.com/user-attachments/assets/42b94805-04eb-4872-9ffe-2278ae674e09)

**Precision Term**

![image](https://github.com/user-attachments/assets/0c637777-d6e5-49a4-a041-44e4351a40ce)

## Ridge Regression vs Lasso Regression

 It is used for regularizing linear models to avoid overfitting and improve predictive performance.
-> Lasso Regression or L1 regularization introduces a penalty based on the absolute value of the coefficients.

![image](https://github.com/user-attachments/assets/15c9375d-b9ff-44e5-a307-13a33ab48bbe)

-> Ridge Regression or L2 regularization adds the squared magnitude of the coefficients as a penalty.

![image](https://github.com/user-attachments/assets/d821c220-6364-4d38-8aef-cee72f14e13e)






















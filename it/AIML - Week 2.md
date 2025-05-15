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

# Math for Machine Learning

## Regression Analysis
Regression analysis is a statistical method for understanding relationships between variables. It is crucial for predictive modeling and interpreting patterns in data. Techniques like linear regression provide the foundation for supervised learning, where the goal is to predict continuous outcomes.











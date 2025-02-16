# 📊 Data Visualization in Python 📉 📈

Like the normal data analysis tools Numpy and Pandas, data visualization is done using the external libraries in Python. Primarily, we here focus on `Matplotlib` and `Seaborn`. Data Visualization is an outstanding way to summarize the analysed data in simpler and engaging way. Let's see how to use them step by step:  

## Importing the libraries:  
#### 1] Matplotlib:
For this, we use the following command in general:  
`import matplotlib.pyplot as plt`  
Alternatively, we can use:  
`from matplotlib import pyplot as plt`  
Both the commands mean the same thing that we are importing the functionalities from the pyplot class in the library matplotlib. In the Jupyter Notebook, for having the output graph inside the notebook interface itself, we add the following "magic" statement:  
`%matplotlib inline`.

#### 2] Seaborn:
The command is:  
`import seaborn as sns`.  

## Matplotlib Functions:
### 1] Standard Line Plot:  
Here the x and y parameters with respect to the axes are passed. The y variable is the dependent parameter and x is the independent one. Here a line straight line is plotted directly joining the points corresponding to the (x, y) value pairs. Syntax:  
`plt.plot(x,y)`
Eg 1:  

```python
x=8
y=9
plt.plot(x,y, marker='o')
plt.show
```  
![point](image-52.png)  

Eg 2:  
```md
import matplotlib.pyplot as plt
X = [1,2,3,4,5,6,7,8,9]
Y = [3,6,2,7,11,12,13,16,12]

plt.plot(X, Y, marker='o')  # 'o' draws markers on each point
plt.show()
```  
![graph](image-53.png)  

### 2] Scatter Plots:
Scatter plots are used in either of the following situations:
- When we have paired numerical data.  
- When there are multiple values of the dependent variable for a unique value of an independent variable.  
- In determining the relationship between variables in some scenarios  
Here, x contains the independent variable, and y contains the dependent variable. You have the option to change the size, color, and shape of the markers with additional attributes in the function.  
Eg:  
```python
df['horsepower']=pd.to_numeric(df['horsepower'], errors='coerce')  # To make the variable a numeric value
df.plot.scatter(x='horsepower', y='price', c='blue', alpha=0.5)
plt.title("Horsepower vs. Price")
plt.show()
```  
![scatter plot](image-54.png)  

### 3] Histogram:
The histogram is typically used to divide the data in a set of bins (either equally in number of bins or ranges) and representing these bins w.r.t. their frequencies of occurance. Here we use the `plt.hist()` method.  
![first](image-55.png)  
Here, the bins were automatically divided from min to max in equal parts. What if I want to set the ranges of the edges myself? Then we first define the custom list ourselves and then set it into the bins attribute.  
![second](image-56.png)
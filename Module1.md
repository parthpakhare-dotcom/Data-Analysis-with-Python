# Module 1:

---
  

## Chapter 1: Understanding the Data

![CSV File in excel](automobilecsv.png)
The data set that we are using is the open dataset by Jeffery C Schlimmer on the used car prices. The data is in CSV (comma seperated values) format.  
In a CSV file, each of the values are seperated by commas.This makes it easier to import in most tools and applications.  

Each line represents the row in the data set.
See the data set on this [link](https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data) or [click](Automobile_data.csv) to download it (cleaner version).  

If you clink on link above, the displayed data doesn't appear to have any heading, but one can modify the csv file to include the headings for each attribute.  

The various parameters in commas respectively will be in the respective coloumns. Like first elements in each of the rows (lines) represent the symbolings describing the risk factor (above 0, it becomes riskier) associated with a particular used car in the row.  
The second attribute normalized losses shows the average loss on a certain car's insurance for a year. This number can range from 65-256 for various types of automobiles like two-door, small, station wagons, sports/specialty, etc.  

Going down, the last and 26th attribute is the "price". This is our target attribute or "label". our goal will be to analyze all the other car features like symbolings, normalized-losses, fuel-type, etc. and based on them predict the price of a car if certain valued for the attributes are passed.  

---
  

## Chapter 2: Python Packages for Data Science  

The Python language has a lot of libraries that we can import to use a collection of in-built functions. These functions make the task of analyzing the data very easy with just a few lines of code.  

_These Libraries are classified as:_  
1] **Scientific Computing** Libraries:- (For calculations)  

***Pandas***: Offer essential data structure and tools for effective data manipulation and analysis. Especially used for 2D tables called data frames, Pandas come with easy indexing functionality.  

***NumPy***: It uses arrays for i/ps and o/ps. It can be extended to objects for matrices.  

**_SciPy_**: It includes functions for mathematical operations like calculus, optimization and visualization.  

2] **Vizualization** Libraries:- (For visualization)
These libraries are the best to represent the results of the data to others as they communicate about the data in visuals.  

**_Matplotlib_**: To make highly customizable plots and graphs  

**_Seaborn_**: Based on Matplotlib, it is a high level visualization library used to generate plots like heat maps, time series and violin plots.  

3] **Algorithmic** Libraries:
These are used to create models based on our data sets using machine learning and make predictions.  

**_Scikit-learn_**: Contains tools for statistical modelling such as regression, classification, clustering, etc. The library is itself built on NumPy, SciPy and Matplotlib.  

**_Statsmodels_**: Explores data, estimate statistical models, and perform statistical tests.

---

## Chapter 3: Importing and Exporting Data in Python

---

## Chapter 4: Getting Started

---

## Chapter 5: Getting Started Analyzing Data in Python

---

## Chapter 6: Accessing Databases with Python

---

## Chapter 7: This is Summary

---
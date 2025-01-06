# 📚 Module 1:

---


## 🌟 Chapter 1: Understanding the Data

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
<p> </p>  
<p> </p>
<p> </p>
  
## 🌟 Chapter 2: Python Packages for Data Science  

The Python language has a lot of libraries that we can import to use a collection of in-built functions. These functions make the task of analyzing the data very easy with just a few lines of code.  

_These Libraries are classified as:_  
1] **Scientific Computing** Libraries:- (For calculations)  

***Pandas***: Offer essential data structure and tools for effective data manipulation and analysis. Especially used for 2D tables called data frames, Pandas come with easy indexing functionality.  

- ***NumPy***: It uses arrays for i/ps and o/ps. It can be extended to objects for matrices.  

- **_SciPy_**: It includes functions for mathematical operations like calculus, optimization and visualization.  

2] **Vizualization** Libraries:- (For visualization)  
These libraries are the best to represent the results of the data to others as they communicate about the data in visuals.  

- **_Matplotlib_**: To make highly customizable plots and graphs  

- **_Seaborn_**: Based on Matplotlib, it is a high level visualization library used to generate plots like heat maps, time series and violin plots.  

3] **Algorithmic** Libraries:  
These are used to create models based on our data sets using machine learning and make predictions.  

- **_Scikit-learn_**: Contains tools for statistical modelling such as regression, classification, clustering, etc. The library is itself built on NumPy, SciPy and Matplotlib.  

- **_Statsmodels_**: Explores data, estimate statistical models, and perform statistical tests.
![Libraries](Libraries.png)

---
<p> </p>  
<p> </p>
<p> </p>

## 🌟 Chapter 3: Importing and Exporting Data in Python

Now, we'll see how to read the data using Python's Panda package.

To read the data using Pandas in Python there are two important factors:  
_  
**1] Format:-**  
This the format in which the file is encoded. It can usually be identified by the ending of the file name (eg CSV, JSON, HDF, XLSX, etc.).  
**2] File path:-**  
This indicates where the file is indicated. It can be the server directory or the remote link on a webpage.
Last time we saw the file data in the .csv format. Even though we cannot fastly make sense of the data in the given format, reading such data with Pandas makes it accessible.  
![Used cars data](csv.png)

### Reading the data in Pandas can be done in three lines:
- Importing the Pandas with a Variable.
- Declare a variable with the value of the path to the CSV file.
- Use the "read_csv" data function to import the data.

Eg:  
`import pandas as pd`                                                                   ## an object pd of class pandas is made  
`url="https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data"` ## a string of url is saved in the variable  
`df=pd.read_csv(url)`                                                                   ## the in-built member fuction read_csv is called by the object  

Or simply as,  
`import pandas as pd`  
`df=pd.read_csv("https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data")`  

Now, an important note is that, the read_csv function considers the first line to be the header by default. But our csv file has no header. Thus, we specify header to none:  
`import pandas as pd`  
`url="https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data"`  
`df=pd.read_csv(url, header=None)`  

![Data frame](image-5.png)

Thus, the dataset is read into the 2D table called the data frame succesfully.  
To test it out, we can print the dataframe by simply writing `df`. But as it may take extra time and resources in some unneeded cases, we can simply print the first n rows as:  
`df.head(50)`  
![Head1](image-2.png)
![Head2](image-3.png)
![Head3](image-4.png)

Similarly, to show the bottom n rows, we use:  
`df.tail(10)`  
![Tail](image.png)

We mentioned `None` for header. Thus, integers were automatically given in their place. If not given in the first columns itslef, a row of header can be given as a list of strings of column names and passed to the `column` attribute in the dataframe like below.  

`headers = ["symboling","normalized-losses","make","fuel-type","aspiration", "num-of-doors","body-style", "drive-wheels","engine-location", "wheel-base", "length","width","height", "curb-weight", "engine-type", "num-of-cylinders", "engine-size","fuel-system", "bore","stroke","compression-ratio","horsepower", "peak-rpm","city-mpg","highway- mpg", "price"]`  
`df.columns=headers`  
`df.head(5)`  

![Columns](image-6.png)


### Exporting the data
After you have done some operations on your dataframe (will be discussed later), if we want to export it as a new csv file in our computer, we simply run the following commands.  
`path=r"C:\Users\HP\Downloads\Exportingautomobiles.csv" ## Directory and desired file name`  
`##Note, we made the string for path a raw string, as String can't process '\' normally`  
`df.to_csv(path)`  

![saved](image-1.png)

This makes the file exported with the `to_csv` function.
In this way, Pandas support import and export of different file formats like:  
`CSV`  
`JSON`  
`EXCEL`  
`SQL`  Eg. `read_sql()` to import and `to_sql()` to export.  

---
  
  
  

## 🌟 Chapter 4: Getting Started Analyzing data in Python

Considering that we've gotten the idea of importing the datasets, let's start with analysing it by using the Pandas.
Pandas has several built in methods that can be used to understand the data type of features or to look at the distribution of data within the dataset. Using these methods gives an overview of the dataset and also points out potential issues such as the wrong data type of features which may need to be resolved later on.  
There are various types of Data. The main data types in Pandas are `object`. `int64` and `float64`. They're the same as the data types `strings`, `int` and `float`, respectively, in the native Python.  
The `datetime` data type is important to show the time relative data.  
Pandas, like normaly in Python langauge, automatically assigns the data type to certain values. But for a number of reasons, the assigned data type can be error prone. Like eg: the column, `car-price` has numerical values and naturally it must be in the numerical data type like `float` to make calculations on it. But the Pandas may assign it with the `object` data type. Similarly, if there's some column about the bumber plates, having assigned the object data type would make more sense.  

When the data tyes method, `dtypes` is applied to the data frame, the data type of the each column is returned in a series. Eg:  
`df.dtypes`  
![column data types](image-7.png)  

Intuitively, most of the data types appearing above are right. Eg, the `make` column consists of variety of names, thus an  `objects`. However, notice that the data for the bore column are understood as `objects`, while they represent the dimensions in engines, thus should be of type `float`. Thus, such types are to be corrected (how will be seen later).  

### Statistical Summary of the dataframe
For this, we use the `describe()` method. For a specific column, it returns:  
- `count`: Number of terms in the column.  
- `mean`: Average column value  
- `std`: Column's standard deviation  
- `min`: Minimum values  
- `max`: Maximum values  
- `25%`: 25% of all the occurances  
- `50%`: 50% of all the occurances  
- `75%`: 75% of all the occurances  
![describe](image-8.png)  

Notice how by default the columns only with numerical data are analysed with the describe function. Though it can work forthe object type as well. To enable the summary of all the columns, we can add an argument `include` with value `"all"`. Now, we can see that for the `object` data type columns, a diff set of statistics is evaluated. Like unique, top and frequency:  
- `unique`: Number of distinct objects in the column   
- `top`: Most frequently occuring object  
- `freq`: Frequency of the top object in the column  
![include all](image-9.png) 
Some values in the table are given as `NaN`, meaning "Not a Number". It's because, that particular statistical metric is not made to calculate the values in a column with the given data type.  
<p> </p>

Another function to check the data set is `info()` function. It gives the consise summary of the data set.  
![info](image-10.png)
---

## 🌟 Chapter 5: Accessing Databases in Python

Let's learn how to access the databases using Python. (•ˋ _ ˊ•) {Many first time occuring terms are italized but are later explained. Keep reading patiently.}  

A database is an organized collection of data that allows easy access, management, and updating. Databases are essential for storing large amounts of structured information, such as in applications, websites, or data analysis.  
**_API Calls_**: It is the mechanism by which a Python program communicates with the _DBMS_.

**API**: An application programming interface is a "set of functions" that you can call to get access to certain type of service. Think of an API as a waiter in a restaurant: you (the application) tell the waiter (API) what you want, and they communicate with the kitchen (DBMS) to bring you the result. In the context of databases:
- A _SQL_ API provides functions to send SQL commands to a DBMS and retrieve results.
- A DB API in Python standardizes database interactions, enabling you to write code that works across multiple database types.  

**SQL**: Structured Query Language (SQL) is the standard language used to communicate with relational databases. It allows you to:
- Retrieve data (`SELECT`).  
- Insert new data (`INSERT`).  
- Update existing data (`UPDATE`).  
- Delete data (`DELETE`).  
- Create or modify database structures (`CREATE`, `ALTER`).  

**Python DB API**: The Python DB API is a standardized interface provided by Python to work with various relational databases. It ensures consistency across various database modules like MySQL, PostgreSQL, or SQLite. Thus, if you understand the Python DB API, you generally do not need to work directly with a SQL API. Your primary task is to write SQL queries (which are universal across SQL-based databases) and use Python DB API methods to interact with the database. Hence, learning how to use the Python DB API is very useful.  

Two core concepts of Python DB APIs:
- Connection Objects: Handle the connection to the database.
- Cursor Objects: Execute SQL commands and fetch results.  
  
**Connection Objects**:
These are the Python objects or entities that represent a connection to the database. They are used to:  
- Establish a link to the database  
- Start, commit, or rollback _transactions_
- Close the connection after use  
  
Methods of (or functions in) Connection Objects:  
- `cursor()`: Create a _cursor_ object to execute queries
- `commit()`: Saves changes made during the current transaction
- `rollback()`: Reverts changes in case of an error
- `close()`: Close the connection  
  
**Cursor Objects**:  
A cursor object is like a pointer to the result of a query. Using its reference, we:  
- Execute SQL queries  
- Navigate through and fetch results row by row  
.    
Cursor Methods:  
- `execute()`: Runs a SQL query
- `fetchone()`: Retrieves the next row of the result set  
- `fetchall()`: Retrieves all rows from the result set
`  
**Transactions**:  
A transaction is a group of operations performed as a single unit. For eg, transferring money between accounts involves two operations:  
- Deducting from one account  
- Adding to another account  
These two are grouped together.  
Forming Transactions ensures either all operations succeed or none take effect. Key terms:  
- `commit()`: Finalizes or saves the transaction  
- `rollback()`: Cancels the transaction  

### Using the DB API to query a Database
Here we see an example of a Python application. Steps to use the Python DB API:  
1) Importing the database module:   
- Eg. `import sqlite3` for the SQLite database to import the entire module. Then we can directly include the connect() function.  
- Eg. If we have a custom made module like, say, `dmodule`, we may import the the connect function like  
`from dmodule import connect`  

2) Establish a connection:  
Use the `connect()` method to put on a connection with the DBMS. Along with the `databasename` parameter, you may even provide with the authenticaton parameters if the method allows:  
- `connection=connect('databasename', 'username', 'pswd')  

3) Create a cursor object:  
Use the connection's `cursor()` method.  
- `cursor = connection.cursor()  

4) Now, we execute the queries using the SQL statements and the cursor method `execute()`. Eg:  
- `cursor.execute('select * from mytable')

5) Fetch results:  
Retrieve the query results via cursor methods.  
- `results = cursor.fetchall()`

6) Close the connection:  
Free resources when done using the `close()` method.
...  
Bonus info:  
#### Buffers:
A buffer is a temporary storage area in memory. In database communication, SQL statements are prepared as text strings in a buffer before being sent to the DBMS.

---

## 🌟 Lesson Summary
### Summary of Key Points

- **Dataset Basics**:
  - Each line in a dataset is a row, and commas separate the values.
  - To understand the data, you must analyze the attributes for each column of data.

- **Python Libraries**:
  - Python libraries are collections of functions and methods that facilitate various functionalities without writing code from scratch.
  - Libraries are categorized into:
    - Scientific Computing
    - Data Visualization
    - Machine Learning Algorithms
  - Many data science libraries are interconnected:
    - Example: Scikit-learn is built on top of NumPy, SciPy, and Matplotlib.

- **Reading Data with Pandas**:
  - The data format and the file path are two key factors for reading data with Pandas.
  - The `read_csv` method in Pandas can read files in CSV format into a Pandas DataFrame.

- **Pandas Data Types**:
  - Pandas has unique data types like `object`, `float`, `int`, and `datetime`.
  - Use the `dtype` method to check each column’s data type; misclassified data types might need manual correction.
  - Knowing the correct data types helps apply appropriate Python functions to specific columns.

- **Statistical Summary in Pandas**:
  - Using `describe()` provides count, mean, standard deviation, min, max, and quartile ranges for numerical columns.
  - Use `include='all'` as an argument to get summaries for object-type columns.
  - The statistical summary helps identify potential issues like outliers needing further attention.

- **Using the `info()` Method**:
  - Gives an overview of the top and bottom 30 rows of the DataFrame.
  - Useful for quick visual inspection.
  - Some statistical metrics may return "NaN," indicating missing values that the program can’t calculate statistics for that specific data type.

- **Python and Databases**:
  - Python can connect to databases through specialized code, often written in Jupyter notebooks.
  - SQL Application Programming Interfaces (APIs) and Python DB APIs (most often used) facilitate the interaction between Python and the DBMS.

- **SQL APIs**:
  - Connect to DBMS with one or more API calls.
  - Build SQL statements as a text string.
  - Use API calls to send SQL statements to the DBMS and retrieve results and statuses.

- **Python DB API**:
  - Python’s standard for interacting with relational databases.
  - Uses **connection objects** to establish and manage database connections.
  - Uses **cursor objects** to run queries and scroll through the results.

- **Connection Object Methods**:
  - `cursor()`: Creates a cursor object.
  - `commit()`: Saves changes to the database.
  - `rollback()`: Cancels uncommitted changes.
  - `close()`: Closes the database connection.

- **Database Operations in Python**:
  - Import the database module.
  - Use the `Connect` API to open a connection.
  - Create a cursor object to run queries and fetch results.
  - Remember to close the database connection to free up resources.


---

## 🌟 Practice Quiz

# Quiz Questions

### **Question 1**
Which of the following commands would you use to retrieve only the attribute datatypes of a dataset loaded as pandas data frame `df`?

```markdown
- `df.info()`
- `df.describe(include=’all’)`
- `df.describe()`
- `df.dtypes`
```

---

### **Question 2**
What description best describes the library, Numpy?

```markdown
- Offers data structure and tools for effective data manipulation and analysis. It provides fast access to structured data.
- A highly efficient array processing library capable of quickly performing mathematical transformation functions on single or multi-dimensional arrays.
- Includes functions for some advanced math problems and scientific processes.
- Includes functions for creating various plots that can be used to create different visualizations for the dataset.
```

---

### **Question 3**
What task does the following code perform?

```python
path='C:\Windows\…\automobile.csv';
df.to_csv(path);
```

```markdown
- Converts a CSV file in the directory specified by the path to a data frame.
- Exports your Pandas data frame to a new CSV file in the location specified by the variable path.
- Loads a CSV file.
- Opens a CSV file specified by the path.
```

---

### **Question 4**
How would you use the `describe()` method with a data frame `df` to get a statistical summary of all the columns in the data frame?

```markdown
- `df.describe(include=“columns”)`
- `df.describe(include=“None”)`
- `df.describe(include=“all”)`
- `df.describe(include=“summary”)`
```
Answers:  

1. **Question 1**:  
   **Answer**: Option 4

2. **Question 2**:  
   **Answer**: Option 2

3. **Question 3**:  
   **Answer**: Option 2

4. **Question 4**:  
   **Answer**: Option 3


---
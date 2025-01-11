# 🌟 Chapter 5: Accessing Databases in Python

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
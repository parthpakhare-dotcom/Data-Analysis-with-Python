# 🌟 Chapter 1: Understanding the Data

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
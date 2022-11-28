Data Mining Lab
===========================

# Catalog
* [Common Libraries](#common-libraries)
	* [Pandas](#pandas)
	* [Matplotlib](#matplotlib)
	* [Seaborn](#seaborn)
	* [Sklearn](#sklearn)
* [references](#references)


## Stages of data mining
* data acquisition
* data cleaning, preparation, and transformation;
	* Removing duplicates
	* Checking for na values 
	* Drop unnecessary columns
* data analysis, modeling, classification, and forecasting;
* report


## Common Libraries
* pandas
* sklearn - for decision trees
* numpy
* seaborn
* matplotlib


### Pandas
* Mostly used for opening and reading csv files
* [Pandas tutorial](https://www.digitalocean.com/community/tutorials/python-pandas-module-tutorial)

* `Pandas basics`
```python
import pandas as pd # Importing the module
df=pd.read_csv('diabetes.csv')  # Here, df stands for data frame
df=pd.read_csv('breast cancer.csv',index_col="id")  # specifying the primary key
df.head(3)  # reads the first 3 rows, if no argument is passed, it will print the first 5 rows
df.tail(3)  # reads the last 3 rows, if no argument is passed, it will print the last 5 rows
df.describe()  # Generate descriptive statistics like mean,standard_deviation,count,25%,75% etc
df['Age'].describe() # Describing only on column
df.shape  # gives the number of rows and columns (r,c) eg. (569,32)
df.info()  # Print a concise summary of a DataFrame. This method prints information about a DataFrame including the index dtype and columns, non-null values and memory usage 
df.value_counts() # Counts unique records in the dataset i.e eliminates duplicates then counts
df['gender'].value_counts()  # counts unique records in the specified column (removes duplicates then counts the records. It also gives count for each occurence e.g Male : 80 ,Female :90)
```

* `Checking for and removing duplicates`
```python
df.duplicated().sum() # Showing the number of duplicated records
df[df.duplicated()] # Best way of showing duplicated records
df[df.duplicated(keep=False)] # Also shows duplicated records
df[df.isin(df[df.duplicated()])].sort_values("sepal_width") # Showing the duplicated records
df.drop_duplicates(inplace=True) # Removing duplicates
```

* `Checking of na values and removing them`
```python
df.isna().sum() # Checking for na values
df.dropna(inplace=True) # Deleting na values

# dropna() - Drop Null/NA Values from DataFrame
```

* `Checking of null values and removing them`
```python
df.isnull().sum() # Counting null values
df.dropna(inplace=True) # Deleting null values

# dropna() - Drop Null/NA Values from DataFrame
```
* `Sorting values`
```python
df.sort_values('Literacy %', ascending=False) # Sorting a single column in ascending order
```

* `Filtering values`
```python
df[df['species']==False] # Filtering values by string
df[df['species'] != "Iris-setosa"] # Filter values that do not match a certain criteria
df[df['Age']>90] # Filtering values by number
df[df['species'].isin(['Iris-virginica','two'])] # Sorting by comparing to a list of values i.e similar to if item in ['one','two']
```

* `Column Operations (Renaming and deleting)`
```python
# Renaming a column
df.rename(columns = {'Old Name':'New Name'}, inplace=True)

# Adding a new column to the data
df['Accepted']="True"
df.head() # To confirm the changes

# Deleting a column
del df['Accepted']
df.pop('Accepted')

# Merging 2 columns to create a new one
df['Total']=(df['Income']+df['Expenses'])
```

* `Viewing data`
```python
# Printing the first 10 rows of the data frame for visualization
df[:10]
```


* `Finding the correlation and plotting`
There are three methods of finding correlation

```python
corr=df.corr(method='kendall')
corr=df.corr(method='pearson')
corr=df.corr(method='spearman')

corr=df.corr() # Use corr() function to find the correlation among the columns in the Dataframe using the ‘Pearson’ method. 
```



### Matplotlib
* Mostly used for plotting
* [Matplotlib Tutorial](https://matplotlib.org/stable/tutorials/introductory/pyplot.html)
* [Matplotlib Tutorial](https://www.geeksforgeeks.org/matplotlib-tutorial/)

* `Basics`
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(10,8)) # Creating a new figure with width = 5 inches and height = 4 inches
```

* `Plotting a heatmap using seaborn`
* We can use the correlation obtain in the previous stage
```python
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```

### sklearn
* for generating decision trees
```
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test
```



### Code Example
```
import numpy as np
import pandas as pd
from matplotlib import pyplot as plt
import seaborn as sn
df=pd.read_csv('diabetes.csv')
```

### References
- https://medium.com/analytics-vidhya/iris-data-prediction-using-decision-tree-algorithm-7948fb68201b
- https://www.kaggle.com/code/osamaeldemerdash/diabetes-prediction-with-decisiontreeclassifier
- https://www.kaggle.com/code/paramutchanthakan/cluster-analysis-using-hierarchical-and-kmean
Data Mining Lab
===========================

# Catalog
* [common-libraries](#common-libraries)
	* [pandas](#pandas)
* [](#)
* [](#)
* [](#)
* [references](#references)


## Stages of data mining
* data acquisition
* data cleaning, preparation, and transformation;
* data analysis, modeling, classification, and forecasting;
* report


## Common Libraries
* pandas
* sklearn - for decision trees
* numpy
* seaborn
* matplotlib


### pandas
* Mostly used for opening and reading csv files
* Example

```python
import pandas as pd # Importing the module
df=pd.read_csv('diabetes.csv')  # Here, df stands for data frame
df=pd.read_csv('breast cancer.csv',index_col="id")  # specifying the primary key
df.head(3)  # reads the first 3 rows, if no argument is passed, it will print the first 5 rows
df.tail(3)  # reads the last 3 rows, if no argument is passed, it will print the last 5 rows
df.describe()  # Generate descriptive statistics like mean,standard_deviation,count,25%,75% etc
df.shape  # gives the number of rows and columns (r,c) eg. (569,32)
df.info()  # Print a concise summary of a DataFrame. This method prints information about a DataFrame including the index dtype and columns, non-null values and memory usage 

df.duplicated().sum()
df.isna().sum()
df['diagnosis'].value_counts()  # counts unique records in the specified column

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
* https: #medium.com/analytics-vidhya/iris-data-prediction-using-decision-tree-algorithm-7948fb68201b
* https: #www.kaggle.com/code/osamaeldemerdash/diabetes-prediction-with-decisiontreeclassifier
* https: #www.kaggle.com/code/paramutchanthakan/cluster-analysis-using-hierarchical-and-kmean
Data Mining Lab
===========================

# Catalog
<li><a href="#markdown-guide">Markdown Guide</a></li>


# Data mining libraries
* pandas`
* sklearn - for decision trees
* numpy
* seaborn
* matplotlib


## LAB 2
### pandas
* for opening and reading csv files
* Example
```
import pandas as pd
df=pd.read_csv('diabetes.csv')
df=pd.read_csv('breast cancer.csv',index_col="id") // specifying the primary key
df.head(3) // reads the first 3 rows
df.tail(3) // reads the last 3 rows
df.describe() // Generate descriptive statistics like mean,standard_deviation,count etc
df.shape // gives the number of rows and columns eg. (569,32)
df.info() // Print a concise summary of a DataFrame. This method prints information about a DataFrame including the index dtype and columns, non-null values and memory usage 

df.duplicated().sum()
df.isna().sum()
df['diagnosis'].value_counts() // counts unique records in the specified column

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
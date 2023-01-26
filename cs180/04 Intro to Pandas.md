Daily Note: [[2023-01-26]] -- [*created*:: 2023-01-26] #cs180 

# Pandas (==Pan==el==Da==taAnaly==s==is)

- DataFrame
- Reading Data
- Selecting Data
- Filtering 
- Grouping/Aggregating
- Joining

--- 

## Import
```python
import pandas as pd
import numpy as np
```

# The Dataframe Object

## Constructing from a dictionary:
```python
data = {
	"name": ['Tom', 'Mark', 'Travis'],
		"class": ['cs180', 'cs180', 'cs180'],
	"grade": [82, 95, 91]
}

grades = pd.DataFrame(data)
```

## Constructing from an array:
```python
array = np.array{
	[
		['Tom', 'cs180', 82]
		['Mark', 'cs180', 95]
		['Travis', 'cs180', 91]
	]
}
headers = ["name", "class", "grade"]

grades_arrayed = pd.DataFrame(arr, columns=headers)

grades2
grades2['name']
arr[:, 0]
```

## Reading/Writing Data
```python
import requests
dta = requests.get("https://<the iris dataset>").text
headers = ['sepal length', 'sepal width', 'petal length', 'petal width', 'class']

rows = []
for row in dta.splitlines():
	if len(row) == 0:
		continue
	rows.append(row.split(","))

iris = pd.DataFrame(rows, columns=headers)
#cast to float type
iris["sepal length"] = iris["sepal length"].astype(float) 
#etc for sepal width, and other numeric values

iris.head(10) #prints out first 10 values
iris.tail(10) #prints out last 10 values


#write to csv (a method on the DataFrame object)
iris.to_csv("iris.csv", index=False) #or index_col=0

#read csv (a function in Pandas)
iris2 = pd.read_csv("iris.csv")
```

## Descriptive Functions
```python
#value counts
iris.value_counts("class") #returns frequency of each 'class'

#describe
summary = iris.describe() #returns a dataframe with summary stats
summary.loc["count"]["sepal length"] #location in DataFrame

iris.dtypes #returns datatypes
```

## Selecting Data
```python
#selecting columns
iris["sepal length"] #a single name
iris[["sepal length", "sepal witdth"]] #a single list of names

#selecting rows
iris.loc[0:10] #strings/ints - Named location (this does 10 rows)
iris.loc["count", "mean", "std"]
iris.iloc[0:5] #always an int for iloc
```

## Mutating a DataFrame
```python
iris.fillna(0, inplace = True)
```

## Plots
```python
iris.hist() #a histogram (of each column)
#and others
```

## Transforming Data 
```python
#adding columns
iris['cost'] = 0.0 #inits all to 0.0

#vectorized column operations
iris['sum'] = iris['sepal length'] + iris['petal length']
#makes a new row that is the sum of sepal && petal length
```

## Filtering
```python
iris.shape #returns shape

iris['sepal length'] < 5.0 #returns a boolean array
filtered = iris[iris['sepal length'] < 5] #make a new DataFrame with only True

iris["class"].unique() #returns the unique values
filtered2 = iris[iris['class'] == 'Iris_virginica']

#return a numpy array
iris.values
```

## Grouping/Aggregating
```python
groups = iris.grouby("class") #key value pairs
for id, block in groups:
	print(id)
	print(block.id)

groups.mean() #DataFrame with means

iris.groupby("class").mean()
```
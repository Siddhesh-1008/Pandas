# Python Pandas & NumPy Interview Revision Notes 🚀

---

# Import Libraries

```python
import pandas as pd
import numpy as np
```

---

# NUMPY REVISION

## Create NumPy Array

```python
np.array([1,2,3])
```

---

## linspace()

👉 Creates equally spaced numbers.

```python
np.linspace(0,10,5)
```

---

## arange()

👉 Creates range of values.

```python
np.arange(0,10,2)
```

---

## zeros()

```python
np.zeros((2,2))
```

---

## ones()

```python
np.ones((3,3))
```

---

## Vector

👉 1D array.

```python
np.array([1,2,3])
```

---

## vstack()

👉 Vertical stacking.

```python
np.vstack((a,b))
```

---

## hstack()

👉 Horizontal stacking.

```python
np.hstack((a,b))
```

---

## column_stack()

👉 Converts arrays into columns.

```python
np.column_stack((a,b))
```

---

## Array Indexing

```python
data[:,1]
data[:,2]
```

👉 Selects all rows of specific column.

---

# PANDAS SERIES

## Create Series

```python
pd.Series()
```

---

## Series using List

```python
my_list = [10,20,30]
pd.Series(my_list)
```

---

## Series using Labels

```python
labels = ['a','b','c']
pd.Series(my_list,index=labels)
```

---

## Series using NumPy Array

```python
arr = np.array([10,20,30])
pd.Series(arr)
```

---

## Series using Dictionary

```python
my_dict = {1:10,2:20,3:30}
pd.Series(my_dict)
```

---

# DATAFRAME CREATION

## Using Dictionary

```python
pd.DataFrame(data)
```

---

## Using List

```python
pd.DataFrame(data2)
```

---

## Add Column Names

```python
pd.DataFrame(data2,columns=cols)
```

---

# DATAFRAME BASIC FUNCTIONS

## head()

```python
df.head()
```

👉 First 5 rows.

---

## tail()

```python
df.tail()
```

👉 Last 5 rows.

---

## shape

```python
df.shape
```

👉 Returns rows and columns.

---

## size

```python
df.size
```

👉 Total elements.

---

## columns

```python
df.columns
```

👉 Shows all column names.

---

## info()

```python
df.info()
```

👉 Datatypes + null values.

---

## describe()

```python
df.describe()
```

👉 Statistical summary.

---

# COLUMN ACCESSING

## Single Column

```python
df['Name']
```

---

## Multiple Columns

```python
df[['Name','Age']]
```

---

## Dot Notation

```python
df.Name
```

---

# ROW ACCESSING

## loc[]

👉 Label based indexing.

```python
df.loc[0]
```

---

## iloc[]

👉 Index based indexing.

```python
df.iloc[0]
```

---

# FILTERING

```python
df[df['Age'] > 25]
```

---

# SORTING

```python
df.sort_values('Salary')
```

---

# MISSING DATA HANDLING

## Missing Values

```python
np.nan
```

---

## isnull()

```python
df.isnull()
```

---

## notnull()

```python
df.notnull()
```

---

## dropna()

```python
df.dropna()
```

👉 Removes rows with null values.

---

## dropna(axis=1)

```python
df.dropna(axis=1)
```

👉 Removes columns with null values.

---

## Threshold

```python
df.dropna(thresh=3)
```

👉 Minimum non-null values required.

---

## fillna()

```python
df.fillna(0)
```

---

## Fill with Mean

```python
df['A'].fillna(df['A'].mean())
```

---

## Fill with Median

```python
df['A'].fillna(df['A'].median())
```

---

## Fill with Mode

```python
df['A'].fillna(df['A'].mode()[0])
```

---

## Forward Fill

```python
df.fillna(method='ffill')
```

---

## Backward Fill

```python
df.fillna(method='bfill')
```

---

# APPLY FUNCTION

```python
df['Salary'].apply(lambda x:x*2)
```

👉 Applies function on every row value.

---

# UNIQUE VALUES

## unique()

```python
df['City'].unique()
```

---

## value_counts()

```python
df['City'].value_counts()
```

---

# RENAME & DROP

## Rename Columns

```python
df.rename(columns={'A':'Age'})
```

---

## Drop Column

```python
df.drop('Age',axis=1)
```

---

# MERGING & JOINING

## merge()

```python
pd.merge(df1,df2,on='id')
```

---

## Inner Join

```python
pd.merge(df1,df2,on='employee_id',how='inner')
```

👉 Common rows only.

---

## Outer Join

```python
pd.merge(df1,df2,on='employee_id',how='outer')
```

👉 All rows from both tables.

---

## Left Join

```python
pd.merge(df1,df2,on='employee_id',how='left')
```

---

## Right Join

```python
pd.merge(df1,df2,on='employee_id',how='right')
```

---

## Merge on Multiple Columns

```python
pd.merge(df1,df2,on=['id','name'])
```

---

# CONCATENATION

## Vertical Concatenation

```python
pd.concat([df1,df2])
```

---

## Horizontal Concatenation

```python
pd.concat([df1,df2],axis=1)
```

---

## Reset Index

```python
pd.concat([df1,df2],ignore_index=True)
```

---

# JOIN

```python
df1.join(df2)
```

---

## Join with Suffix

```python
df1.join(df2,lsuffix='_left',rsuffix='_right')
```

---

# GROUPBY

## Basic GroupBy

```python
df.groupby('Company')
```

---

## GroupBy Multiple Columns

```python
df.groupby(['Company','Department'])
```

---

## sum()

```python
df.groupby('Company').sum()
```

---

## mean()

```python
df.groupby('Company').mean()
```

---

## count()

```python
df.groupby('Company').count()
```

---

## max()

```python
df.groupby('Company').max()
```

---

## min()

```python
df.groupby('Company').min()
```

---

## Select Specific Column

```python
df.groupby('Company')['Sales'].sum()
```

---

## agg()

```python
df.groupby('Company').agg(['sum','mean','max'])
```

---

## describe()

```python
df.groupby('Company').describe()
```

---

## get_group()

```python
df.groupby('Company').get_group('Google')
```

---

# PIVOT TABLE

## Basic Pivot Table

```python
pd.pivot_table(df)
```

---

## Pivot Table Example

```python
pd.pivot_table(
    df,
    values='Sales',
    index='Region',
    columns='Product'
)
```

---

## aggfunc='sum'

```python
aggfunc='sum'
```

---

## aggfunc='mean'

```python
aggfunc='mean'
```

---

## aggfunc='count'

```python
aggfunc='count'
```

---

## Multiple Aggregations

```python
pd.pivot_table(
    df,
    values='Sales',
    index='Region',
    columns='Product',
    aggfunc=['sum','mean']
)
```

---

## Fill Missing Values

```python
fill_value=0
```

---

## Margins

```python
margins=True
```

---

# CROSSTAB

## Basic Crosstab

```python
pd.crosstab(df['Region'],df['Product'])
```

---

## Normalize

```python
pd.crosstab(
    df['Region'],
    df['Product'],
    normalize=True
)
```

---

## Crosstab with Margins

```python
pd.crosstab(
    df['Region'],
    df['Product'],
    margins=True
)
```

---

# DATE RANGE

```python
pd.date_range('2023-01-01',periods=20)
```

---

# STRING OPERATIONS

## str.replace()

```python
df['Episodes']=df['Episodes'].str.replace(' eps','')
```

---

## split()

```python
start,end = txt.split('-')
```

---

## find()

```python
txt.find('(')
txt.find(')')
```

---

## String Slicing

```python
txt[start:end+1]
```

---

# CUSTOM FUNCTIONS

## Extract Episodes

```python
def extract_episodes(txt):

    start = txt.find('(')
    end = txt.find(')')

    return txt[start:end+1]
```

---

## Apply Function

```python
df['Episodes']=df['Title'].apply(extract_episodes)
```

---

## Extract Timestamp

```python
def extract_ts(txt):

    start = txt.find(')')

    return txt[start+1:start+20]
```

---

## Create Timestamp Column

```python
df['Timestamp']=df['Title'].apply(extract_ts)
```

---

# MONTH COUNT EXTRACTION

## period_range()

```python
pd.period_range(start,end,freq='M')
```

---

## Count Months

```python
len(pd.period_range(start,end,freq='M'))
```

---

## Create Months Count Column

```python
df['Months_Count']=df['Timestamp'].apply(count_months)
```

---

# TOP VALUES

## max()

```python
df['Episodes'].max()
```

---

## Highest Row Using Condition

```python
df[df['Episodes']==df['Episodes'].max()]
```

---

## nlargest()

```python
df.nlargest(1,'Episodes')
```

---

## Top 5 Rows

```python
df.nlargest(5,'Episodes')
```

---

## sort_values()

```python
df.sort_values('Episodes',ascending=False)
```

---

# DISPLAY SETTINGS

## Show Full Text

```python
pd.set_option('display.max_colwidth',None)
```

---

## Reset Option

```python
pd.reset_option('display.max_colwidth')
```

---

# IMPORTANT INTERVIEW MEMORY TRICKS 🚀

```text
loc      → label based
iloc     → index based
merge    → combine using key
concat   → stack dataframes
groupby  → grouping
agg      → calculations
pivot    → summary table
crosstab → counting combinations
apply    → function on each row
nlargest → top highest rows
```

---

# QUICK INTERVIEW REVISION 🚀

```python
# DataFrame
pd.DataFrame()
df.head()
df.tail()
df.shape
df.size
df.columns
df.info()
df.describe()

# Selection
df['col']
df[['c1','c2']]
df.loc[]
df.iloc[]

# Missing Values
df.isnull()
df.dropna()
df.fillna()

# Merge & Join
pd.merge()
pd.concat()
df.join()

# GroupBy
df.groupby()
sum()
mean()
count()
agg()

# Pivot
pd.pivot_table()
pd.crosstab()

# String Operations
str.replace()
find()
split()
apply()

# Top Values
max()
nlargest()
sort_values()
```

---

# END 🚀

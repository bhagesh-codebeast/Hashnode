## Pandas basics & tricks every Data Science / Bioinformatics aspirant must know.

### Hi and Welcome

If you want to chose Data Science or Bioinformatics as a career, fetching,  [cleaning  & organizing the data ](https://bhagesh-codebeast.github.io/Data_Cyclopes/) in a specific shape will be your day to day task before applying any analysis technique or machine learning algorithms. Here in this post, I'll be sharing few quick and basic pandas codes which will help you get your data in shape.

Pandas library in python is built on *NumPy*; It is a fundamental library in python for data analysis, pre-processing , e.t.c. it is rich in methods used for data munging & a quick **Exploratory Data Analysis** (EDA). There are two main objects in pandas, they are pandas **Series** & **DataFrame**.

You can see it as a database whose primary purpose is not for storing data, but easily manipulate and query data, which are features of every database management system.

The pandas spells covered in this article are :

1. Importing Pandas
2. Reading Datasets from files
3. Exporting Data
4. Create test objects
5. Viewing/Inspecting Data
6. Selection / Filtering a specific data
7.  [Data Cleaning / Wrangling](https://bhagesh-codebeast.github.io/Data_Cyclopes/) 
8. Filter, Sort & Groupby
9. Join & Combine
10. Statistics



#### Enough! Let's get down to business.

****

1. Importing Pandas
-------------------------------------------------------
****

```
import pandas as pd
``` 


2. Reading Datasets from files
-------------------------------------------------------
****
Basic file types pandas can handle are CSV, Excel file, html file and the list goes on ...!


- Reading **CSV** file
```
data = pd.read_csv(".../FilePath/file.csv") 
``` 
- Reading **TSV** file
```
data = pd.read_table(".../FilePath/file.tsv")
``` 
- Reading **Excel** file
```
data = pd.read_excel(".../FilePath/file.xls")
``` 
- Read from a **SQL** table/database
```
data = pd.read_sql(query, connection_object)
``` 
- Read from a **JSON** formatted string, URL or file
```
data = pd.read_json(json_string)
``` 
- From a **dict**, keys for columns names, values for data as lists
```
data = pd.DataFrame(dict)
``` 
- Takes the contents of your **clipboard** and passes it to read_table()
```
data = pd.read_clipboard()
``` 
- Parses an **html URL**, string or file and extracts tables to a list of dataframes
```
data = pd.read_html(url)
``` 


3. Exporting Data
-------------------------------------------------------
****

Use these commands to export a DataFrame to CSV, .xlsx, SQL, or JSON.

[Here `df` is a `DataFrame` fetched from a dataset or a file ]

- Write to a CSV file
```
df.to_csv("filename.csv")
``` 
- Write to an Excel file
```
df.to_excel("filename.xls")
``` 
- Write to a SQL table
```
df.to_sql(table_name, connection_object)
``` 
- Write to a file in JSON format
```
df.to_json("filename.json")
``` 


4. Create test objects
-------------------------------------------------------
****
Before we proceed let's import one more essential module in Python
```
import numpy as np
```

These commands can be useful for creating **test segments** 
> For when you're in a mood to play 

- Create 5 columns and 20 rows of random floats
```
pd.DataFrame(np.random.rand(20,5))
```
- Create a series from an iterable my_list
```
pd.Series(my_list)
```
- Add a date index
```
df.index = pd.date_range('1900/1/30', periods=df.shape[0])
```


5. Viewing/Inspecting Data
-------------------------------------------------------
****
Use these commands to take a look at specific sections of your pandas DataFrame or Series instead of scrolling all the way top just to look at your data.

> Rule of thumb: Don't be shy 

- First n rows of the DataFrame
```
df.head(n)
```
- Last n rows of the DataFrame
```
df.tail(n)
```
- Number of rows and columns
```
df.shape
```
- Index, Datatype and Memory information
```
df.info()
```
- Summary statistics for numerical columns
```
df.describe()
```
- View unique values and counts
```
s.value_counts()
```
- Unique values and counts for all columns
```
df.apply(pd.Series.value_counts)
```


![innovation-technology.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1596116335769/-79JsnNmx.png)


6. Selection / Filtering a specific data
-------------------------------------------------------
****
Use these commands to select a specific subset of your data.

> Nobody is asking you to not be picky 

[Here `s` implies that it's a `Series`]

- Returns column with label col as Series
```
df[col]
```
- Returns columns as a new DataFrame
```
df[[col1, col2]]
```
- Selection by index
```
s.loc['index_one']
```
- Selection by position
```
s.iloc[0]
```
- First row
````
df.iloc[0,:]
```
- First element of first column
```
df.iloc[0,0]
```

An easy way to remember how  `loc`  & `iloc` work is that  `i`  in  `iloc`  stands for ***integer*** i.e.  `iloc`  takes in integers as row & column values while `loc` accepts row number  & column names.

> Trust me,  `iloc`  has a crush on ***integer***


7.  Data Cleaning / Wrangling
-------------------------------------------------------
****
Use these commands to perform a variety of data cleaning tasks.
> Oh.. GOD I love these ...

- Rename columns
```
df.columns = ['a','b','c']
```
- Checks for null Values, Returns Boolean Arrray
```
pd.isnull()
```
- Opposite of pd.isnull()
```
pd.notnull()
```
- Drop all rows that contain null values
```
df.dropna()
```
- Drop all columns that contain null values
```
df.dropna(axis=1)
```
- Drop all rows have have less than n non null values
```
df.dropna(axis=1,thresh=n)
```
- Replace all null values with x
```
df.fillna(x)
```
- Replace all null values with the mean (mean can be replaced with almost any function from the statistics module)
```
s.fillna(s.mean())
```
- Convert the datatype of the series to float
```
s.astype(float)
```
- Replace all values equal to 1 with 'one'
```
s.replace(1,'one')
```
- Replace all 1 with 'one' and 3 with 'three'
```
s.replace([1,3],['one','three'])
```
- Mass renaming of columns
```
df.rename(columns=lambda x: x + 1)
```
- Selective renaming
```
df.rename(columns={'old_name': 'new_ name'})
```
- Change the index
```
df.set_index('column_one')
```
- Mass renaming of index
```
df.rename(index=lambda x: x + 1)
```



8. Filter, Sort & Groupby
-------------------------------------------------------
****

Use these commands to filter, sort, and group your data.
> You see *Data* doesn't like to be lonely, neither with a lot of it's own kind ! pretty, selectively social.

- Rows where the column col is greater than 0.5
```
df[df[col] > 0.5]
```
- Rows where 0.7 > col > 0.5
```
df[(df[col] > 0.5) & (df[col] < 0.7)]
```
- Sort values by col1 in ascending order
```
df.sort_values(col1)
```
- Sort values by col2 in descending order
```
df.sort_values(col2,ascending=False)
```
- Sort values by col1 in ascending order then col2 in descending order
```
df.sort_values([col1,col2],ascending=[True,False])
```
- Returns a groupby object for values from one column
```
df.groupby(col)
```
- Returns groupby object for values from multiple columns
```
df.groupby([col1,col2])
```
- Returns the mean of the values in col2, grouped by the values in col1 (mean can be replaced with almost any function from the statistics module)
```
df.groupby(col1)[col2]
```
- Create a pivot table that groups by col1 and calculates the mean of col2 and col3
```
df.pivot_table(index=col1,values=[col2,col3],aggfunc=mean)
```
- Find the average across all columns for every unique col1 group
```
df.groupby(col1).agg(np.mean)
```
- Apply the function np.mean() across each column
```
df.apply(np.mean)
```
- Apply the function np.max() across each row
```
nf.apply(np.max,axis=1)
```


9. Join & Combine
-------------------------------------------------------
****
Use these commands to combine multiple dataframes into a single one.
> Urgh...! Why ? **Data** Why?...

- Add the rows in df1 to the end of df2 (**columns** should be **identical**)
```
df1.append(df2)
```
- Add the columns in df1 to the end of df2 (**rows** should be **identical**)
```
pd.concat([df1, df2],axis=1)
```
- *SQL-style join* the columns in df1 with the columns on df2 where the rows for col have identical values. `how` can be one of `left`, `right`, `outer`, `inner` . 
[Useful with dataframes constitute rows of varying number]
```
df1.join(df2,on=col1,how='inner')
```


10. Statistics
-------------------------------------------------------
****
Use these commands to perform various statistical tests. (These work on series as well.)
> Short & Sweet

- Summary statistics for numerical columns
```
df.describe()
```
- Returns the mean of all columns
```
df.mean()
```
- Returns the correlation between columns in a DataFrame
```
df.corr()
```
- Returns the number of non-null values in each DataFrame column
```
df.count()
```
- Returns the highest value in each column
```
df.max()
```
- Returns the lowest value in each column
```
df.min()
```
- Returns the median of each column
```
df.median()
```
- Returns the standard deviation of each column
```
df.std()
```


##### **Conclusion** : Obtaining the  *Super Powers* of the pandas library in Python is a must for one to be very **successful** at data manipulation, especially if you want to reduce the time taken in data cleansing.

****
### Hooraay...! Finally ... 

#### that was a lot I know, but this article isn't going anywhere, take your time learn them slowly. P.s. make sure to *bookmark* it.



> The best way to learn these is to learn these.

Okay fineeee.... this was the last one. If you have made it till here, You're **AWESOME... ! ** Checkout how I have used pandas to visualize relationship between **  [COVID-19 & World Happiness ](https://www.kaggle.com/bhageshcodebeast/covid19-vs-world-happiness) ** on Kaggle. Warning [****cute COVID picture in the above article****]


> Support me by hitting the **subscribe** button on my **YouTube** channel  [CodeBeast](https://www.youtube.com/channel/UCHPrekRJR20NV4RxFRe6vBw)

## Keep Coding , Keep Slaying.

%[https://youtu.be/irvkjrHMAj0]
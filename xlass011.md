# Pandas

[SOURCE](https://pandas.pydata.org/pandas-docs/stable/getting_started/intro_tutorials/index.html)

`Pandas` is a fast, powerful, flexible and easy to use open source data analysis and manipulation tool,
built on top of the Python programming language. 

To load the pandas package and start working with it, import the package.

To manually store data in a table, create a `DataFrame`.

A DataFrame is a 2-dimensional data structure that can store data of different types (including characters, integers, floating point values, categorical data and more) in columns.

Pandas provides a lot of functionalities, each of them a method you can apply to a `DataFrame` or `Series`. As methods are functions, do not forget to use parentheses ().

example code

```
In [7]: df["Age"].max()
Out[7]: 58
```

to a series

```
In [8]: ages.max()
Out[8]: 58
```

The `describe()` method provides a quick overview of the numerical data in a DataFrame.

```
In [9]: df.describe()
Out[9]: 
             Age
count   3.000000
mean   38.333333
std    18.230012
min    22.000000
25%    28.500000
50%    35.000000
75%    46.500000
max    58.000000
```

pandas provides the ```read_csv()``` function to read data stored as a csv file into a pandas DataFrame. pandas supports many different file formats or data sources out of the box (csv, excel, sql, json, parquet, …), each of them with the prefix read_*.

```
titanic = pd.read_csv("data/titanic.csv")
```

Head() to specify the first rows you want to see

Whereas `read_*` functions are used to read data to pandas, the `to_* methods` are used to store data. The to_excel() method stores the data as an excel file. 

The method `info()` provides technical information about a DataFrame

To select a `single column`, use square brackets [] with the column name of the column of interest.

To select multiple columns, use a list of column names within the selection brackets [].

```
In [8]: age_sex = titanic[["Age", "Sex"]]

In [9]: age_sex.head()
Out[9]: 
    Age     Sex
0  22.0    male
1  38.0  female
2  26.0  female
3  35.0  female
4  35.0    male
```

The `notna()` conditional function returns a True for each row the values are not a Null value. As such, this can be combined with the selection brackets [] to filter the data table.

The loc/iloc operators are required in front of the selection brackets []. When using loc/iloc, the part before the comma is the rows you want, and the part after the comma is the columns you want to select.

```
In [23]: adult_names = titanic.loc[titanic["Age"] > 35, "Name"]

In [24]: adult_names.head()
Out[24]: 
1     Cumings, Mrs. John Bradley (Florence Briggs Th...
6                               McCarthy, Mr. Timothy J
11                             Bonnell, Miss. Elizabeth
13                          Andersson, Mr. Anders Johan
15                     Hewlett, Mrs. (Mary D Kingcome) 
Name: Name, dtype: object
```

To create a new column, use the [] brackets with the new column name at the left side of the assignment.

***The rename()** function can be used for both row labels and column labels. Provide a dictionary with the keys the current names and the values the new names to update the corresponding names.

The value_counts() method counts the number of records for each category in a column

With `DataFrame.sort_values()`, the rows in the table are sorted according to the defined column(s). The index will follow the row order.

Multiple tables can be concatenated both column-wise and row-wise using the `concat function`.

For database-like merging/joining of tables, use the `merge function.`

# Initial Exploration

Exploratory Data Analysis (EDA) is the process of cleaning and reviewing data.

- The general initial step in EDA is `data.info()` which provides information about the data types and missing values in each column.
- Another method is `data.describe()` which gives a statistical summary of numerical columns.

# Data Validation
We can perform data validation using the following techniques:

- **Changing Data Type:** The `astype()` method can be used to change the data type of a column.

- **Filtering Data Types:** To view only specific data types, you can use the `select_dtypes("")` method followed by `head()` to display the first few rows.

# Data Summarization
Data summarization involves grouping the data and applying aggregate functions. Some useful techniques are:

- **Grouping Data:** The `groupby()` method is used to group the data based on a column.

- **Aggregating Functions:** Various aggregating functions can be applied to the grouped data. Here are some examples:
  - `sum()`: Computes the sum of values in a column.
  - `count()`: Calculates the number of non-null values in a column.
  - `min()`: Finds the minimum value in a column.
  - `max()`: Finds the maximum value in a column.
  - `var()`: Computes the variance of values in a column.
  - `std()`: Calculates the standard deviation of values in a column.

- **Applying Multiple Aggregating Functions:** The `agg()` method allows you to apply multiple aggregating functions to the data. You can use the following syntax:
  ```python
  data.groupby("column").agg(
      a=("column", func),
      b=("column1", func)
  )
  ```

Here are the code snippets corresponding to the techniques mentioned in the previous notes:

## Initial Exploration

```python
# Display information about the dataset
data.info()

# Generate descriptive statistics of numerical columns
data.describe()
```

## Data Validation

```python
# Change the data type of a column
data["column_name"] = data["column_name"].astype("desired_data_type")

# Filter and view specific data types
filtered_data = data.select_dtypes("desired_data_type").head()
```

## Data Summarization

```python
# Group the data and calculate aggregate statistics
grouped_data = data.groupby("column")

# Applying aggregating functions to the grouped data
sum_values = grouped_data["column1"].sum()
count_values = grouped_data["column2"].count()
min_value = grouped_data["column3"].min()
max_value = grouped_data["column4"].max()
variance = grouped_data["column5"].var()
std_deviation = grouped_data["column6"].std()

# Applying multiple aggregating functions using the agg() method
result = data.groupby("column").agg(
    sum_column=("column1", sum),
    count_column=("column2", count),
    min_column=("column3", min),
    max_column=("column4", max),
    var_column=("column5", var),
    std_column=("column6", std)
)
```

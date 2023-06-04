# Introduction to Seaborn

Seaborn is a powerful data visualization library in Python that provides a high-level interface for creating informative and attractive statistical graphics. It is built on top of Matplotlib, another popular plotting library. Seaborn is particularly useful for working with structured datasets and producing visually appealing visualizations.

## Advantages of Seaborn
1. **Easy to use:** Seaborn provides a simple and intuitive API for creating various types of plots, allowing users to quickly generate visualizations with just a few lines of code.
2. **Works well with pandas:** Seaborn seamlessly integrates with Pandas, a popular data manipulation library in Python. This integration makes it easy to visualize Pandas DataFrames and Series directly using Seaborn functions.
3. **Built on top of Matplotlib:** Seaborn enhances Matplotlib's capabilities by providing a higher-level interface and introducing additional plot types and styles. It takes advantage of Matplotlib's functionality while simplifying the code required to create visually appealing plots.

## Getting Started

To use Seaborn, you need to import it along with Matplotlib:

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

## Scatter Plot

Scatter plots are useful for visualizing the relationship between two continuous variables. Seaborn provides a convenient function for creating scatter plots:

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(x, y)
plt.show()
```

## Count Plot

Count plots are used to display the frequency of categorical variables. Seaborn's `countplot()` function is specifically designed for this purpose:

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(x='category')
plt.show()
```

## Working with DataFrames

Seaborn integrates well with Pandas DataFrames, allowing you to easily visualize data from structured datasets:

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.DataFrame(data)
sns.countplot(x='key', data=df)
plt.show()
```

## Tidy Dataframes

Seaborn works best with tidy dataframes, which follow the principles of tidy data. Tidy data is organized in a way that each variable has its own column, each observation has its own row, and each value has its own cell. Seaborn's plotting functions are optimized for working with this tidy data format.

## Adding a Third Variable with Hue

You can enhance your plots by incorporating a third variable using the `hue` parameter. It allows you to differentiate data points based on a categorical variable:

```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.scatterplot(x, y, data=df, hue='variable')
plt.show()
```

## Adjusting Hue Order

You can control the order of the hue levels using the `hue_order` parameter. It allows you to specify the desired order of the categories:

```python
sns.scatterplot(x, y, data=df, hue='variable', hue_order=['level1', 'level2'])
plt.show()
```

## Customizing Hue Colors

You can assign custom colors to the hue levels by providing a dictionary of colors using the `palette` parameter:

```python
hue_colors = {'key1': 'color1', 'key2': 'color2'}
sns.scatterplot(x, y, data=df, hue='variable', palette=hue_colors)
plt.show()
```

Note: The specific colors can be specified using Matplotlib's color codes, such as named colors, RGB values, or hexadecimal color codes.

## Hue in Different Plot Types

The `hue` parameter is available in various other plot types provided by Seaborn, allowing you to incorporate an additional

 categorical variable for differentiation.
﻿# Introduction to Relational Plots and Subplots

## Relational Plot

A relational plot is used to visualize the relationship between two variables, x and y.

### Introducing `relplot()`

Instead of using a scatter plot, we can use the `relplot()` function from the seaborn library for general relational plots.

To use `relplot()`, we need to import the seaborn library:
```python
import seaborn as sns
```

#### Basic usage:
```python
sns.relplot(x, y, data, kind="scatter")
```

#### Subplots:
We can also create subplots using the `col` or `row` parameter:
```python
sns.relplot(x, y, data, kind, col or row)
```

#### Wrapping columns:
To wrap the columns in the subplot, we can use `col_wrap` parameter:
```python
sns.relplot(x, y, data, kind, col, col_wrap)
```

#### Order of columns:
To specify the order of the columns, we can use the `col_order` parameter:
```python
sns.relplot(x, y, data, kind, col, col_wrap, col_order)
```

### Customizing Scatter Plot

We can customize the scatter plot by adjusting the size, style, and transparency of the data points.

#### Deciding the size of the point:
To change the size of the points based on a variable, we can use the `size` parameter:
```python
sns.relplot(x, y, data, kind, size="variable name")
```

#### Deciding the style of the point:
To change the style of the points based on a variable, we can use the `style` parameter:
```python
sns.relplot(x, y, data, kind, style="variable name")
```

#### Adjusting the transparency of the point:
To control the transparency of the points, we can use the `alpha` parameter. The range of the `alpha` variable is [0, 1]:
```python
sns.relplot(x, y, data, kind, alpha=variable)
```

## Introduction to Line Plots

A line plot is useful for tracking the same variable over time or displaying the mean values.

### Line Plot

We can use the `line` option in `relplot()` to create a line plot:
```python
sns.relplot(x, y, data, kind="line")
```

### Subgrouping in Line Plots

We can subgroup the lines in a line plot using the `hue` or `style` parameters:
```python
sns.relplot(x, y, data, kind="line", hue, style)
```

### Creating Markers Across the Line

To create markers across the line, we can use the `markers` parameter:
```python
sns.relplot(x, y, data, kind="line", hue, markers)
```

### Ignoring Dash Lines

If we want to ignore the dash lines representing confidence intervals, we can use the `dashes=False` parameter:
```python
sns.relplot(x, y, data, kind="line", style, dashes=False)
```

### Replacing Confidence Interval with Standard Deviation

To replace the confidence interval with standard deviation, we can use the `ci="sd"` parameter:
```python
sns.relplot(x, y, data, kind="line", ci="sd")
```

These features and options in seaborn can be used to create insightful relational plots and subplots to visualize and analyze the relationships between variables.

﻿# Count plots and Bar plots
### Categorical plots
- Barplots and Countplots are generally used most for plotting the categorical daata
- Such as comparisons between groupsa

**Catplot**
- catplot is similar to relplot but is used for categorical data
```
import matplotlib.pyplot as plt
import seaborn as sns
#Using catplot for count
sns.catplot(x="column_name",data=Dataframe_variable,kind="count"

plt.show()

```
### Manipulating the countplot
- Changing the order
```
sns.catplot(x,data,kind,order=list_variable)
```
### Bar plots
- These plots are used for displaying the means 

```
sns.catplot(x,y,data,kind="bar")
```
- Adding confidence Interval
```
sns.catplot(x,y,data,ci)
```

### Creating box plot
- The box plot shows the distribution of data
- It shows the median, spread, skewness and outliers of data
```
sns.catplot(x,y,data,kind="box")
```
- Deleting the outliers
```
sns.catplot(x,y,data,kind="box",sym="")
```
- Changing the whiskers
```
sns.catplot(x,y,data,kind,whis=variable or list)
#showing min or max values
sns.catplot(x,y,data,kind,whis=[0,100])
```
## Point plots
- It shows the mean of quantitative variable
- It is similar to line plot but this is used for categorical variable for comparison

- Creating a point plot
```
sns.catplot(x,y,data,kind="point",hue)
```

- Disconnecting the points
```
sns.catplot(x,y,data,kind,hue,join=False)
```
- Displaying the median
```
sns.catplot(x,y,data,kind,estimator=median)
```

- Customizing the CI
```
sns.catplot(x,y,data,kind,capsize)
# To make the Class interval 0
sns.catplot(x,y,data,kind,ci=None)

```
﻿# Changing Plot Style and Color

## Setting the Style of the Figure
To set the style of a figure in seaborn, you can use the `sns.set_style()` function. Seaborn provides several preset styles that you can choose from, such as `white`, `dark`, `whitegrid`, and more.

Example:
```python
import seaborn as sns

sns.set_style("whitegrid")
```

## Changing the Colors
To change the colors in seaborn plots, you can use the `sns.set_palette()` function. There are two types of palettes you can use: diverging and sequential. 

You can also create custom palettes by specifying a list of colors.

Example:
```python
import seaborn as sns

# Using a diverging palette
sns.set_palette("coolwarm")

# Using a sequential palette
sns.set_palette("Blues")

# Creating a custom palette
custom_palette = ["#FF0000", "#00FF00", "#0000FF"]
sns.set_palette(custom_palette)
```

## Changing the Scale
To change the scale of the context in seaborn, you can use the `sns.set_context()` function. There are several scales available: "paper", "notebook", "talk", and "poster".

Example:
```python
import seaborn as sns

sns.set_context("poster")
```

## Adding Titles and Labels
Seaborn provides functions to add titles and labels to your plots, similar to matplotlib.

Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Creating a plot
sns.lineplot(x, y)

# Adding a title
plt.title("My Plot")

# Adding labels
plt.xlabel("X Label")
plt.ylabel("Y Label")

plt.show()
```

## FacetGrid vs AxesSubplot
Seaborn creates two types of objects: FacetGrid and AxesSubplot. To determine the type of object, you can use the `type()` function. FacetGrid consists of one or more AxesSubplots.

Example:
```python
import seaborn as sns

# Creating a FacetGrid
g = sns.catplot(x, y, data, kind)

# Checking the type of object
print(type(g))  # <class 'seaborn.axisgrid.FacetGrid'>
```

## Adding a Title to FacetGrid
To add a title to a FacetGrid, you can access the underlying figure (`g.fig`) and use the `suptitle()` function.

Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Creating a FacetGrid
g = sns.catplot(x, y, data, kind)

# Adding a title to the figure
g.fig.suptitle("My FacetGrid Title")

plt.show()
```

## Adding a Title to AxesSubplot
To add a title to an AxesSubplot, you can use the `set_title()` function.

Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Creating a box plot
g = sns.boxplot(x, y, data, kind)

# Adding a title to the subplot
g.set_title("My Box Plot Title")

plt.show()
```

## Titles for Subplots
To add titles to subplots in a FacetGrid, you can use the `set_titles()` function and specify a formatting string that includes the column name.

Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Creating a FacetGrid
g = sns.catplot(x, y, data, kind, col="category")

# Adding titles to subplots
g.set_titles("This is {col_name}")

plt.show()
```

## Adding Axis Labels and Rotating Ticks
To add axis labels

 to a plot in seaborn, you can use the `set()` function and specify the `xlabel` and `ylabel`. To rotate the ticks on the x-axis, you can use `plt.xticks(rotation=90)`.

Example:
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Creating a plot
g = sns.lineplot(x, y)

# Adding axis labels
g.set(xlabel="X Label", ylabel="Y Label")

# Rotating x-axis ticks
plt.xticks(rotation=90)

plt.show()
```
﻿## Intermediate Data Visualization with Seaborn

Seaborn is a popular data visualization library in Python. Here are some examples of its usage:

### Histograms and Distribution Plots
- To create a histogram, use `sns.histplot(df)`.
- To create a distribution plot with a histogram and a kernel density estimate, use `sns.displot(df, bins=10, kde=True)`.
- Alternatively, you can use a kernel density estimate plot with a rug plot and filled areas using `sns.displot(df, kind="kde", rug=True, fill=True)`.
- To create an empirical cumulative distribution function (ECDF) plot, use `sns.displot(df, kind="ecdf")`.

### Regression Plots
- To display a scatter plot with a regression line, use `sns.regplot(data=df, x=x, y=y)`.
- Another method to create regression plots is `sns.lmplot(data=df, x=x, y=y)`.
- For faceting, there are two options: hue-based faceting and col/row-based faceting.
  - Hue-based faceting: Use `sns.lmplot(data=df, x=x, y=y, hue=hue)` to create a single plot with different colors based on a categorical variable.
  - Col or row-based faceting: Use `sns.lmplot(data=df, x=x, y=y, col=col)` to create two or more plots based on a categorical variable.

Note: The code examples provided assume that `df` is a DataFrame containing the data, `x` and `y` are the column names representing the variables of interest, and `hue` and `col` are optional categorical variables used for faceting.

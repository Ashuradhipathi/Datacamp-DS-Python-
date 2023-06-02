# Python
Python shell is a place to write code and get immediate results.
Python scripts are simply text files  with extension .py consisting of Python commands that are executed.
 `print` command is used to print contents/output from scripts.
 
### Variable
 a specific case-sensitive name used to store/named memory locations. Call up a variable value through variable name.

### DataTypes
`type()` is used to find to find the datatype of  a token.[function]
**float** - real numbers
**int** - integers
**str** - string, text
**bool** - True, False

## Lists
- **[ ]**
- A list is a name given to a collection of values(any typ, even lists)
- Lists contain the references of the stored values
- when you copy a list and alter it, it affects the original list
- use `list()` or slicing to select values to copy

### Subsetting lists
`list_name[index]` indices start from 0(zero indexing)
- Negative indexing lets you select from the end

### Slicing
-allows to select multiple values in list
`list_name[start:end]` start-inclusive, end- exclusive
a[:5] - from start to 5
a[2:] - from index 2 to end of the list

### Manipulating Lists
- list_name[index] = value
- slicing can be used for manipulation
- old_list+[values] = new_list
- `del(list_name[index])`

## Functions
-Piece of reusable code
**Example** (Self Explanatory)
`max()`
`len()`
`round(_number,_digits)`
`round(_number)`
`help(functn_name)` 

### Methods
- functions that belong to objects
- **Example** 
- `list_name.index(index)`
- `list_name.count(value)`
- `list_name.append(value)` some methods change the objects that call them
- `string_value.capitalize()`
- `string_value.replace(original,To_be_replaced_with)`

## Packages
Each script is a module consisting of functions, methods , objects etc
Related modules are stored in packages
**To Install Packages**
```python 
python3 get-pip.py
pip3 install <package_name>

#To use a package it ha sto be imported first
import <package_name>

#using alias
import <package_name> as <alias>

#To import specific parts
from <package_name> import <part_name>
```

**Example**
```python 
#import <package_name>
import numpy 

#using alias
import numpy as np

#To import specific parts
from numpy import array

#most preferable
import numpy as np
np.array()
```



```python 
Numpy
```

﻿# Python Toolbox

## User-defined Function
A user-defined function is a function that is defined by the user. We use the `def` keyword to define a function.

```python
def function_name():
    # Writing some code
```

### Function Parameters
Function parameters are the arguments passed to a function when it is called.

### Docstrings
A docstring is a string that provides a brief description of the function and its purpose. It helps in documenting the function.

```python
def function_name():
    """This function does nothing."""
    pass
```

## Multiple Parameters and Multiple Return Values
A function can accept more than one parameter by specifying them in the function definition.

```python
def function_name(p1, p2):
    x = p1 + p2
    return x
```

A function can also return multiple values by returning them as a tuple or any other iterable.

```python
def function_name(p1, p2):
    nt = (p1, p2)
    return nt
```

By using the above examples, you can define functions with multiple parameters and return multiple values in Python.

﻿# Scope and User-defined Functions

In Python, there are three types of scopes:

1. Global Scope: Variables defined in the main body of a program have a global scope and can be accessed from anywhere in the program.

2. Local Scope: Variables defined inside a function have a local scope and can only be accessed within that function.

3. Built-in Scope: This scope contains names of built-in functions and modules that are available for use in any part of the program.

To make a variable globally available, we can use the `global` keyword.

## Nested Functions
A nested function is a function defined inside another function. It has access to variables from the enclosing function's scope.

```python
def outer(a):
    def inner(r):
        return r
    return inner

s = outer(r)  # outer
s(r)  # inner
```

## Using `nonlocal`
By using the `nonlocal` keyword inside a nested function, we can change the value of a variable defined in the enclosing function.

## Scope Order: LEGB
The order in which Python searches for variables is as follows:
Local Scope -> Enclosing Functions -> Global Scope -> Built-in Scope

## Default and Flexible Arguments

### Default Arguments
Default arguments are used to provide a default value for a parameter if no argument is passed during the function call.

```python
def power(number, pow=1):
    return number ** pow
```

### Flexible Arguments
Flexible arguments allow a function to accept any number of arguments.

#### Flexible Arguments: *args
By using `*args` as a parameter, we can pass a variable number of positional arguments to the function.

```python
def fun(*args):
    return args
```

#### Flexible Arguments: **kwargs
By using `**kwargs` as a parameter, we can pass a variable number of keyword arguments to the function.

```python
def func(**kwargs):
    return kwargs
```

The above examples demonstrate how to use default and flexible arguments in Python functions.

# Lambda Functions

Lambda functions, also known as anonymous functions, are small and inline functions in Python that can be defined without a name. These functions are typically used when we need a simple, one-line function for a specific task. Lambda functions are called using the keyword `lambda` followed by the parameters and a colon, and then the expression or operation to be performed.

Here's an example of a lambda function that takes two parameters and returns their sum:

```python
fun = lambda param1, param2: param1 + param2
```

# Anonymous Functions

Anonymous functions allow us to apply a function to each item in a sequence. The `map()` function in Python can be used to apply a given function to each item of a sequence and return the results as a new list. Similarly, the `filter()` function can be used to filter out items from a sequence based on a given function.

Here's an example of using `map()` and `filter()` functions:

```python
# Applying a function to each item in a sequence
result = map(func, seq)

# Filtering items from a sequence
result = filter(func, seq)
```

# Error Handling

Error handling, also known as exception handling, is the process of dealing with errors or exceptions that occur during the runtime of a program. Python provides mechanisms to catch and handle exceptions to prevent the program from crashing when an error occurs.

# Handling Exceptions

In Python, we can handle exceptions using the `try-except` statement. The code that might raise an exception is placed inside the `try` block, and if an exception occurs, it is caught by the corresponding `except` block. The `except` block specifies the type of exception to catch and the code to execute when that exception occurs.

Here's an example of a `sqrt()` function that calculates the square root of a number, and handles the exception if the input is not a valid number:

```python
def sqrt(x):
    try:
        return x ** 0.5
    except:
        print("x must be an int or float")
```

# Raising an Error

In Python, we can raise our own exceptions using the `raise` keyword. This allows us to explicitly raise an exception when a certain condition is met or an error occurs. By raising an exception, we can communicate and handle errors in a more controlled manner.


﻿# Introduction to Iterators

An iterator is an object that allows us to loop over a sequence of items. In Python, we use iterables to create iterators. Iterables are objects that can return one item at a time when iterated upon.

Let's take a look at how to iterate using a loop:

```python
word = "DAMN"
it = iter(word)
next(it)
print(*it)
```

In the code above, we create an iterator `it` from the string `word`. The `next()` function is used to retrieve the next item from the iterator. In this case, it prints the remaining items in the iterator after the first item is consumed.

Similarly, we can create an iterator from a file object and iterate over its contents:

```python
file = open("file.txt")
i = iter(file)
next(i)
```

In the above code, we open a file called "file.txt" and create an iterator `i` from it. The `next()` function retrieves the next line from the file.

Next, let's explore some useful functions for working with iterators:

## Playing with Iterators

### Enumerate

The `enumerate()` function allows us to assign a number to each item in an iterable. It returns pairs of index and value as tuples.

```python
for index, item in enumerate(iterable):
    # Do something with index and item
```

### Zip

The `zip()` function combines two or more iterables into a single iterable of tuples. Each tuple contains elements from corresponding positions of the input iterables.

```python
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
zipped = zip(list1, list2)
for item in zipped:
    # Do something with the zipped items
```

To unzip the items, you can use the `*` operator inside the `zip()` function:

```python
unzipped = zip(*zipped)
```

## Iterating over Data

When dealing with large datasets, we may need to process the data in smaller chunks instead of loading the entire dataset into memory. The `pandas` library provides a convenient way to iterate over large CSV files using the `read_csv()` function with the `chunksize` parameter.

```python
import pandas as pd

result = []
for chunk in pd.read_csv("data.csv", chunksize=1000):
    result.append(sum(chunk["x"]))

total = sum(result)
print(total)
```

In the above code, we read the CSV file "data.csv" in chunks of 1000 rows at a time. We then calculate the sum of the "x" column for each chunk and store the results in a list. Finally, we sum up all the chunk results to obtain the total.

These examples provide a basic understanding of iterators and how to work with them in Python.

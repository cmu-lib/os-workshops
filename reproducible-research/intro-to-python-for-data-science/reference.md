---
layout: reference
---

## Reference

## [Running and Quitting](__pages/01-run-quit.md)
- Python files have the `.py` extension.
- Can be written in a text file or a [Jupyter Notebook][jupyter].
  - Jupyter notebooks have the extension `.ipynb`
  - Jupyter notebooks can be opened from [Anaconda](https://docs.continuum.io/anaconda/install) or through the command line by entering `$ jupyter notebook`
    - Markdown and HTML are allowed in markdown cells for documenting code.

## [Variables and Assignment](__pages/02-variables.md)
- Variables are stored using `=`.
  - Strings are defined in quotations `'...'`.
  - Integers and floating point numbers are defined without quotations.
- Variables can contain letters, digits, and underscores `_`.
  - Cannot start with a digit.
  - Variables that start with underscores should be avoided.
- Use `print(...)` to display values as text.
- Can use indexing on strings.
  - Indexing starts at 0.
  - Position is given in square brackets `[position]` following the variable name.
  - Take a slice using `[start:stop]`. This makes a copy of part of the original string.
    - `start` is the index of the first element.
    - `stop` is the index of the element after the last desired element.
- Use `len(...)` to find the length of a variable or string.

## [Data Types and Type Conversion](__pages/03-types-conversion.md)
- Each value has a type. This controls what can be done with it.
  - `int` represents an integer
  - `float` represents a floating point number.
  - `str` represents a string.
- To determine a variables type, use the built-in function `type(...)`, including the variable name in the parenthesis.
- Modifying strings:
  - Use `+` to concatenate strings.
  - Use `*` to repeat a string.
  - Numbers and strings cannot be added to on another.
    - Convert string to integer: `int(...)`.
    - Convert integer to string: `str(...)`.

## [Built-in Functions and Help](__pages/04-built-in.md)
- To add a comment, place `#` before the thing you do not with to be executed.
- Commonly used built-in functions:
  - `min()` finds the smallest value.
  - `max()` finds the largest value.
  - `round()` rounds off a floating point number.
  - `help()` displays documentation for the function in the parenthesis.
    - Other ways to get help include holding down `shift` and pressing `tab` in Jupyter Notebooks.

## [Libraries](__pages/05-libraries.md)
- Importing a library:
  - Use `import ...` to load a library.
  - Refer to this library by using `module_name.thing_name`.
    - `.` indicates 'part of'.
- To import a specific item from a library: `from ... import ...`
- To import a library using an alias: `import ... as ...`
- Importing the math library: `import math`
  - Example of referring to an item with the module's name: `math.cos(math.pi)`.
- Importing the plotting library as an alias: `import matplotlib as mpl`

## [Reading Tabular Data into DataFrames](__pages/06-reading-tabular.md)
- Use the pandas library to do statistics on tabular data. Load with `import pandas as pd`.
  - To read in a csv: `pd.read_csv()`, including the path name in the parenthesis.
    - To specify a column's values should be used as row headings: `pd.read_csv('path', index_col='column name')`, where path and column name should be replaced with the relevant values.
- To get more information about a DataFrame, use `DataFrame.info`, replacing `DataFrame` with the variable name of your DataFrame.
- Use `DataFrame.columns` to view the column names.
- Use `DataFrame.T` to transpose a DataFrame.
- Use `DataFrame.describe` to get summary statistics about your data.

## [Pandas DataFrames](__pages/07-data-frames.md)
- Select data using `[i,j]`
  - To select by entry position: `DataFrame.iloc[..., ...]`
    - This is inclusive of everything except the final index.
  - To select by entry label: `DataFrame.loc[..., ...]`
    - Can select multiple rows or columns by listing labels.
    - This is inclusive to both ends.
  - Use `:` to select all rows or columns.
- Can also select data based on values using `True` and `False`. This is a Boolean mask.
  - `mask = subset > 10000`
  - We can then use this to select values.
- To use a select-apply-combine operation we use `data.apply(lambda x: x > x.mean())` where `mean()` can be any operation the user would like to be applied to x.

## [Plotting](__pages/08-plotting.md)
- The most widely used plotting library is `matplotlib`.
  - Usually imported using `import matplotlib.pyplot as plt`.
  - To plot we use the command `plt.plot(time, position)`.
  - To create a legend use `plt.legend(['label1', 'label2'], loc='upper left')`
    - Can also define labels within the plot statements by using `plt.plot(time, position, label='label')`. To make the legend show up, use `plt.legend()`
  - To label x and y axis `plt.xlabel('label')` and `plt.ylabel('label')` are used.
- Pandas DataFrames can be used to plot by using `DataFrame.plot()`. Any operations that can be used on a DataFrame can be applied while plotting.
  - To plot a bar plot `data.plot(kind='bar')`

~~~
import matplotlib.puplot as plot
plt.plot(time, position, label='label')
plt.xlabel('x axis label')
plt.ylabel('y axis label')
plt.legend()
~~~
{: .language-python}

## Glossary

{:auto_ids}
Arguments
:     Values passed to functions.

Array
:     A container holding elements of the same type.

Boolean
:     An object composed of `True` and `False`.

DataFrame
:     The way Pandas represents a table; a collection of series.

Element
:     An item in a list or an array. For a string, these are the individual characters.

Function
:     A block of code that can be called and re-used elsewhere.

Global variable
:     A variable defined outside of a function that can be used anywhere.

Index
:     The position of a given element.

Jupyter Notebook
:     Interactive coding environment allowing a combination of code and markdown.

Library
:     A collection of files containing functions used by other programs.

Local Variable
:     A variable defined inside of a function that can only be used inside of that function.

Mask
:     A boolean object used for selecting data from another object.

Method
:     An action tied to a particular object. Called by using `object.method`.

Modules
:     The files within a library containing functions used by other programs.

Parameters
:     Variables used when executing a function.

Series
:     A Pandas data structure to represent a column.

Substring
:     A part of a string.

Variables
:     Names for values.

{% include links.md %}

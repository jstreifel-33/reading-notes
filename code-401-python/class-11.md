# Data Analysis Basics

## What is Jupyter Lab

[Source: JupyterLab Docs - Overview](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)

JupyterLab is a web-based user interface for Project Jupyter. It enables work with Jupyter notebooks, text editors, terminal, and custom components.

JupyterLab offers a unified model for viewing and handling data formats, with support for CSV, JSON, Markdown and many more formats.

JupyterLab uses the same server and notebook document format as classic Jupyter Notebook.

## Numpy

[Source: DataQuest - Numpy Tutorial](https://www.dataquest.io/blog/numpy-tutorial-python/)

Numpy is a Python data analysis package.

### Working with CSV

Data is commonly stored in a csv file, and the `csv` package can be used to interpret these files using `csv.reader`.

The `list` type can be used to ensure that the results end up as a list of lists.

```python
#from reading:
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))
```

Using `csv.reader` will produce all values a strings, so be sure to parse to floats before working with extracted data.

### Numpy 2D Arrays

Numpy works with multidimensional arrays a little differently than usual. In a NumPy array, the number of dimensions is called the `rank`, and each dimension is an `axis`. In the case of 2D arrays, the rows are the first axis, and the columns are the second axis.

### Creating a NumPy Array

`numpy.array` is used to create NumPy arrays. All values must be the same type.

Passing a list of lists into `numpy.array` will automatically generate a 2D array with the appropriate axes.

`array.shape` can be used to see how many rows and columns a NumPy array has.

### Alternative Array Creation

`numpy.zeros((x,y))` can be used to make an array with every value as 0.

`numpy.random.rand(x,y)` can be used to make an array of random values between 0 and 1.

`numpy.genfromtxt()` can be used to directly interpret a file and generate an array.

### Indexing NumPy Arrays

Numpy is zero indexed, and when accessing values, indices are given in order of axis. `array_2d[0,2]` will access the value in the first row, and third column of an array.

Slices can also be performed with the same notation. `array_2d[1,:3]` will grab row 1, columns 0, 1, 2 values. An entire row or column (or both!) can be selected by using just `:`.

Values can be assigned like any other assignment. `array_2d[0,4] = 5`. Assignments can also be used with slicing to assign values to all positions in a slice.

### NumPy Data Types

[Full list of NumPy Data Types](https://numpy.org/doc/stable/reference/arrays.dtypes.html)

Major data types:

* `float` - numeric floating point data
* `int` - integer data
* `string` - character data
* `object` - Python objects

Data types can be converted using the `.astype(type)` method. It will convert the contents of an array to the provided type, if possible.

### NumPy Array Operations

When a basic operator is used on an array, the operation will be applied to each element in the array. Operations like this return a new array entirely.

Using an assignment operator like `+=` will modify the array in place instead.

Using operators between two arrays will perform the operation between pairs of elements.

### Broadcasting

Elementwise operations require two arrays to be the same size. In cases where this isn't true, numpy performs broadcasting.

* The last dimensions of each array are compared.
  * If the dimension lengths are equal, or one or more of the dimensions is length 1, carry on.
  * If the dimensions lengths are not equal and no dimensions have length 1, there's an error.
* Continue checking dimensions until out of dimensions.

```python
#compatible arrays
A: (50,3)
B: (3,)
#compatible arrays
A: (1,2)
B: (50,2)
#incompatible arrays
A: (50,50)
B: (49,49)
```

[More detailed explanation of broadcasting](https://numpy.org/doc/stable/user/basics.broadcasting.html)

### NumPy Array Methods

* `.sum()` - returns the sum of all values in an array
* `.shape()` - returns the shape of an array
* `.mean()` - returns the mean value of an array
* `.std()` - returns the standard deviation of an array
* `.min()` - returns the minimum value in an array
* `.max()` - returns the maximum value in an array

### Comparisons and Subsetting

Using a comparison operator on a NumPy array or slice will return an array of booleans based on performing the comparison on each element.

This can be used to filter data based on conditional expressions.

```python
#From reading:
high_quality = wines[:,11] > 7
wines[high_quality,:][:3,:]

#filters for wines with a quality greater than 7.
```

For an easy reference, use this [numpy cheatsheet](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf) from dataquest.io!

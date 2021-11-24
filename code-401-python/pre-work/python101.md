# **How to Python**

## **Basic Concepts**

## **Strings & Variables**

## **Control Structures**

### **List Functions**

* `List.append(value)` - adds a value to the end of an existing list. Returns none
* `len(list)` - returns the **length** of a list
* `List.insert(index, value)` - inserts `value` at any specified position in a list
* `List.index(value)` - finds the first occurrence of a `value` and returns its index
* `max(list)` `min(list)` - returns the highest or lowest value in a list
* `list.count(item)` - returns count of how many times `item` occurs in a list
* `list.remove(item)` - removes an object from a list
* `list.reverse()` - reverses the items in a list

### **`while` Loops**

* while loops repeat code as long as a condition evaluates to **true**

```python
i = 0
while i < 4:
  print(i)
  i += 1

# prints 0 1 2 3
```

* `break` can be used to end an infinite loop by placing it inside a conditional.
* `continue` ends the current iteration and starts the next iteration.

### **`for` Loops**

* The `for` loop is used to iterate over a given sequence, such as lists or strings.

```python
words = ['hello', 'world', 'spam', 'eggs']
for word in words:
  print(word + '!')

# hello!
# world!
# spam!
# eggs!
```

### **Range**

* `range(num)` returns a sequence of numbers.
* By default, it starts from 0 and stops **before** the specified number.
* `range(start, stop)` - A second argument can be included to change the start point. The start number **will** be included in the range, while the stop number **will not** be included in the range.
* `range(start, stop, step)` - A third argument can be included to determine the **interval** that steps increase by.
  * `range(20, 5, -2)` - A **negative step value** can be used to generate a range of decreasing numbers.

## **Functions and Modules**

### **Code Reuse**

* When writing code, try to abide by DRY - Don't Repeat Yourself
* The opposite principle is WET - Write Everything Twice
* DRY code is easier to maintain and can be achieved using **functions**

### **Functions**

In python, functions are created using the `def` statement. They are invoked using `function_name()`.

```python
def my_fun():
  print('hello')
  print('world')

my_fun()
```

**NOTE:** Functions must be defined before they are called.

### **Function Arguments**

When defining a function, arguments can be declared inside of the parentheses ().

```python
def print_sum_twice(x, y):
  print(x + y)
  print(x + y)

print_sum_twice(3, 2)
# 5
# 5
```

### **Returning from Functions**

`return` can be used to make a function output a result. It cannot be used outside of a function definition.

Upon return from a function, execution is stopped.

```python
def add_numbers(x, y):
  total = x + y
  return total
  print("this won't be printed")
```

### **Comment and Docstrings**

**Comments** are annotations to make code easier to understand. They do not affect how code is run. Comments are annotated using an octothorpe `#`. Python doesn't have general purpose multiline comments.

```python
x = 365 #Comments can be inline
y = 7
#They can also have their own line
```

**Docstrings** are created under the first line of a function definition. They are retained throughout runtime and can be inspected at runtime. A docstring can include multiple lines of text and is enclosed by `"""` before and after the text:

```python
def shout(word):
  """
  Print a word with an
  exclamation mark added.
  """
  print(word + '!')

shout("hello")
```

### **Functions as Objects**

After definition, functions behave similarly to any other value. They can be assigned and reassigned to variables.

Functions can also be used as arguments in other functions. When used as an argument, functions do not need to include their parentheses.

```python
def square(x):
  return x * x
#accepts func as argument and prints result of executing on x
def test(func, x):
  print(func(x))
#execute.
test(square, 42)
#prints 1764
```

### **Modules**

Modules are pieces of code that have already been written to fulfill common tasks. They are accessed using the `import` keyword, with module variables and functions accessed using `module_name.var` notation.

```python
#imports math module, with all included variables and functions
import math

#only imports specified values from math module, separated by a comma (,)
from math import pi, sqrt

#imports from module and assigns new name
from math import sqrt as square_root
```

**NOTE:** Trying to import an unavailable module will result in an ImportError.

### **The Standard Library & pip**

There are 3 types of modules in Python: those you write yourself, those you install from external sources, and those that are preinstalled with Python.

Preinstalled libraries are known as the **standard library**.

Many third-party Python modules are stored in the **Python Package Index (PyPI)**. Third party libraries can be installed with a program called **pip**. Example: `pip install library_name`

## **Exceptions & Files**

### **Exceptions**

Exceptions occur when something goes wrong in code, such as incorrect code or input. When this happens, then program immediately stops.

Some common exceptions are:

* ImportError: an import fails
* IndexError: a list is indexed with an out-of-range number
* NameError: an unknown variable is used
* SyntaxError: the code can't be parsed properly
* TypeError: a function is called on a value of an inappropriate type
* ValueError: a function is called on a value of the correct type but with an inappropriate value.

**NOTE:** Third-party libraries often define their own exceptions. Read the docs!

### **Exception Handling**

Exceptions in Python are handled using `try/except` statements. Code in the `try` block attempts to execute. If an exception is encountered, execution stops and code in the `except` block is run.

```python
# From sololearn.com:
try:
  num1 = 7
  num2 = 0
  print(num1 / num2)
  print("Done calculation")
except ZeroDivisionError:
  print("An error ocurred")
  print("due to zero division")
```

A single `try` statement an be followed by multiple different `except` statements for handling different exceptions.

An `except` statement without any exception specified will *catch all errors.*

### **finally**

`finally:` can be placed at the end of a `try/except` block to specify code that will run no matter what.

Code in a `finally` code block runs even if an uncaught exception occurs in the preceding blocks (including exceptions in the `except` block).

### **Raising Exceptions**

`raise` can be used to manually throw an exception. You must specify a **type** when raising an exception.

Arguments can be included in raised errors to provide more detail:

```python
# From sololearn.com
name = "123"
raise NameError("Invalid name!")
```

Inside of an `except` block, `raise` can be used to raise whatever exception occurred.

### **Assertions**

The `assert` keyword can be used to perform a sanity-check in code. `assert` will test a given condition and throw an exception if it evaluates false.

```python
# From sololearn.com
print(1)
assert 2 + 2 == 4
print(2)
assert 1 + 1 == 3
#Exception will be thrown and execution will stop
print(3)
```

`assert` can take a second argument, passed to the error raised if the assertion fails.

`assert (temp >= 0), "Colder than absolute zero!"`

### **Opening Files**

Python can read and write file contents. Before editing, a file must be opened using the `open` function, the argument of which is the file path:

```python
my_file = open("filename.txt")
```

A second argument can be used to specify the *mode* used to open a file:

* `"r"` - read mode (default)
* `"w"` - write mode, for rewriting contents. Creates new file if it doesn't exist.
* `"a"` - append mode, for adding new content
* `"b"` - can be added to open in **binary** mode, which is used for non-text files.

When done with a file, you should close it. this is done using `close()`:

```python
# closes file from previous example
my_file.close()
```

### **Reading Files**

A file opened in text mode can be read using `.read()`

A number can be provided as an argument specify how many bytes of a file to read. Negative values will return the entire contents.

After all contents are read, further reading will return an empty string.

The `.readlines()` method can be used to return a list of individual lines in a file.

`for` can also be used to iterate through lines of an opened file.

### **Writing Files**

Files can be written to using the `.write()` method.

**CAUTION:** When opening a file in write mode, the file's existing content is deleted.

the `.write()` method returns the number of bytes written to a file, if successful.

### **Working with Files**

Best practice dictates that files should always be closed after work is done. A good way to ensure this is the use of `try/finally`:

```python
#From sololearn.com
try:
  f=open("file.txt")
  print(f.read())
finally:
  f.close()
```

Another way to accomplish this is by using `with` statements. This allows for the creation of a temporary variable, only accessible inside the following code block. **The file is automatically closed at the end of the statement.**

```python
# file is opened as f
with open("filename.txt") as f:
  print(f.read())
# f is closed automatically at end of block
```

## **More Types**

### **None**

`None` is used to represent the absence of a value, similarly to `null` in other languages:

* Evaluates as False when used as a boolean
* Represented by an empty string in the Python console
* Any function without an explicit return returns `None`

### **Dictionaries**

Dictionaries are data structures that map keys to values. Can be indexed similarly to lists, using square brackets.

```python
# Think objects from JS!
samus = {
  "varia_suit": True,
  "arm_cannon": True,
}
print(samus["varia_suit"])
```

Trying to index a key that doesn't exist will return a **KeyError**.

Dictionary keys must be **immutable**. Using a mutable value as a key will cause a TypeError.

### **Dictionary Functions**

Dictionary keys can be assigned values. New keys can also be assigned values.

```Python
samus["varia_suit"] = False
samus["gravity_suit"] = True
```

`in` and `not in` can be used to determine the presence of a key in a dictionary.

```Python
print("gravity_suit" in samus)
# True

print("missile" in samus)
# False

print("missile" not in samus)
# True
```

`get` behaves similarly to indexing, but can return another specified value is the key provided doesn't exist: `samus.get("morph_ball", "upgrade not found")`

### **Tuples**

Tuples are like lists, but they are immutable. A tuple is enclosed in parentheses ().

```Python
planets = ("ZDR", "SR388", "Zebes", "Phaaze", "Tallon IV", "K-2L", "Dark Aether", "Elysia")
```

Tuple values are still indexed by number, but trying to reassign an index value will cause a TypeError.

**NOTE:** A tuple can also be created without parentheses by simply separating values with commas.

```Python
#Also a valid tuple assignment
planets = "ZDR", "SR388", "Zebes", "Phaaze", "Tallon IV", "K-2L", "Dark Aether", "Elysia"
```

### **List Slices**

List slices are a more advanced way of retrieving values from a list. Similarly to `range` the second index number in a slice is not included in the result.

List slices return a new list containing the index values specified.

```Python
hunters = ["Samus", "Noxus", "Spire", "Kanden", "Sylux", "Trace", "Weavel"]
print(hunters[2:5])
#['Spire', 'Kanden', 'Sylux']
```

Omitting the first or second number in a slice is taken to be the start or end of the list, respectively.

```Python
print(hunters[:5])
#['Samus', 'Noxus', 'Spire', 'Kanden', 'Sylux']
print(hunters[2:])
#['Spire', 'Kanden', 'Sylux', 'Trace', 'Weavel']
```

Similarly to `range`, a third number can be included in slices to specify step size.

```Python
print(hunters[1:6:2])
#['Noxus', 'Kanden', 'Trace']
print(hunters[::3])
#['Samus', 'Kanden', 'Weavel']
```

Negative values can be used to count from the end of a list instead of the beginning. They can also be used for step value to perform a slice backwards.

**NOTE:** `list[::-1]` is a common and simple way to reverse a list.

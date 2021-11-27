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

Omitting the first or second number in a slice is taken to specify the start or end of the list, respectively.

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

### **List Comprehensions**

List comprehensions are a way to quickly create lists with specific rules.

```Python
squares = [i**2 for i in range(4)]
print(squares)
#[0, 1, 4, 9]
```

List comprehensions can also include `if` statements:

```Python
evens = [i**2 for i in range(10) if i**2 % 2 == 0]
print(evens)
# [0, 4, 16, 36, 64]
```

Trying to create a very large or extensive list will result in a **MemoryError**. This is solved with *generators*, which will be covered later.

### **String Formatting**

String formatting is used to substitute values into a string, instead of converting and adding values as done in previous examples.

```Python
nums = [3, 4, 5]
string = "Numbers: {0} {1} {2}".format(nums[0], nums[1], nums[2])
print(string)
# 'Numbers: 3 4 5'
```

In the above example, each argument of `.format()` corresponds to a number in curly braces of the preceding string.

String formatting can also be done with named arguments.

```Python
msg = 'My name is {name} and I am {age} years old'
print(msg.format(name='Bob', age=27))
# 'My name is Bob and I am 27 years old'
```

### **Useful Functions**

* String Functions
  * `str.join(list)` - joins a list of strings with another string as a separator
  * `str.replace(orig, new)` - replaces on substring inside a string with another
  * `str.startswith(substr)`/`str.endswith(substr)` - determine if there is a substring at the start or end of a string (True/False)
  * `str.lower()`/`str.upper()` - change the case of a string
  * `str.split(separator)` - The opposite of join. Makes a string into a list of strings using a separator.
* Numeric Functions
  * `max`/`min` - find the maximum or minimum value in some numbers or a list.
  * `abs` - find the distance from zero of a number (absolute value)
  * `round` - round an number to a certain number of decimal places
  * `sum` - find the total of a list.
* List Functions
  * `all`/`any` - take a list as an argument and return True if all or any arguments evaluate to True
  * `enumerate` - iterates through values and indices simultaneously, as tuples.

### **Text Analyzer**

Example project from sololearn:

```Python
# From sololearn.com
def count_char(text, char):
  count = 0
  for c in text:
    if c == char:
      count += 1
  return count

filename = input('Enter a filename: ')
with open(filename) as f:
  text = f.read()

for char in "abcdefghijklmnopqrstuvwxyz":
  perc = 100 * count_char(text, char) / len(text)
  print("{0} - {1}%".format(char,round(perc,2)))
```

Idk, pretty cool guess. Prints percentage of characters that each letter takes up in a file.

## **Functional Programming**

### **Intro to Functional Programming**

Functional programming is programming based around functions.

**Higher-order functions** are functions that accept other functions as arguments.

**Pure Functions** are functions with no side effects. Their output is entirely depending on provided arguments, and will always be the same given the same values as arguments.

Memoization is possible with pure functions, and involves storing the results of a certain input for recall later, instead of executing a function multiple times for the same input.

### **Lambdas**

`lambda` syntax is Python's way of creating anonymous functions. It consists of `lambda arg: function`

```Python
# From sololearn
def my_fun(f, arg):
  return f(arg)

my_fun(lambda x: 2*x*x, 5)
```

Lambda functions can only do things that require a single expression. (*no code blocks like in JS*)

Lambda functions can also be assigned to variables and used like normal functions. As a general rule, it's better to use `def` in cases where a function will be assigned.

### **map & filter**

`map(f, iterable)` accepts a function and iterable as arguments, and returns a new iterable with the function applied to each argument.

A lambda can be used in place of the function argument, if desired.

`filter(f, iterable)` removes items that don't evaluate true in a given function.

**NOTE:** Both `map` and `filter` must be explicitly converted to a list if printing is desired, by wrapping in `list()`

### **Generators**

Generators are a type of iterable. They don't allow for arbitrary indices, but can be iterated through with `for` loops.

Generators are created using functions and the `yield` statement. `yield` is what defines a generator.

```Python
# from sololearn
def countdown():
  i = 5
  while i > 0:
    yield i
    i -=1

for i in countdown():
  print(i)
```

Since generators only yield one item at a time, they don't have a memory restriction, and can be **infinite**.

Finite generators can be converted to lists by using the `list()` function.

Generators also result in improved performance, on account of lower memory usage.

### **Decorators**

Decorators are a way of modifying functions using other functions.

```Python
# From sololearn
def decor(func):
  def wrap():
    print("=====")
    func()
    print("=====")
  return wrap

def print_text():
  print("Hello world!")

decorated = decor(print_text)
# Executes wrap() with print_text() inside!
decorated()
```

Wow. A variable containing a function can be reassigned with a wrapped version, and Python allows for wrapping a function at definition using `@`:

```Python
#From Sololearn

def print_text():
  print("Hello world!")
print_text = decor(print_text)
#the below and above lines accomplish the same task.
#print_text will be wrapped in decor when invoked.
@decor
def print_text():
  print("Hello world!")
```

### **Recursion**

Recursion at the most fundamental level involves a function calling itself. A classic example is the **facorial** function:

```Python
def facotrial(x):
  if x == 1:
    return 1
  else:
    return x * factorial(x-1)
```

In this example 1! = 1 and is known as our **base case**, or the condition that breaks out of the recursion and doesn't involve further function calls.

Recursive functions can be infinite. This often happens when a base case if forgotten or incorrect. Infinitely recursive functions will result in a `RuntimeError`.

Recursion can also be indirect, in cases where one one function calls a second, which then calls the first, and so on.

```Python
# Fibonacci sequence using recursion
# (from sololearn):
def fib(x):
  if x == 0 or x == 1:
    return 1
  else: 
    return fib(x-1) + fib(x-2)
```

### **Sets**

Sets are similar to lists and dictionaries. They are created using `{values...}` or `set()`. To create an empty set, `set()` must be used, as `{}` will create an empty dict.

* Sets share certain operations with lists, such as `in` and `len`
* Sets are unordered, and cannot be indexed
* **Cannot** contain duplicate elements
* Instead of `.append()`, use `.add()`
* `.remove()` removes a specific element
* `.pop()` removes an arbitrary element

Mathematical operators can be used to combine sets:

* `|` union - combines two sets to form a new one with the items in either
* `&` intersection - gets items only in both
* `-` difference - gets items in the first set but not the second
* `^` symmetric difference - gets items in either set, but not both

### **itertools**

itertools is a standard library containing useful functions for functional programming:

* `count(num)` - counts up infinitely from a value (iterable)
* `cycle(iterable)` - infinitely iterates through an iterable
* `repeat` - repeats an object, either infinitely or a specific number of times
* `takewhile` - takes items from an iterable while a predicate function remains true
* `chain` - combines several iterables into one
* `accumulate` - returns a running total of values in an iterable

## **Object Oriented Programming**

### **Classes**

In python, objects are created using **classes**.

A class describes what an object will be, but is separate from the object itself. It is essentially a blueprint used to create an object.

```Python
class Cat:
  def __init__(self, color, legs):
    self.color = color
    self.legs = legs

felix = Cat("ginger", 4)
stumpy = Cat("brown", 3)
```

`__init__` is called when an instance of a class is created, and is the most important method in a class.

All methods must have `self` as their first parameter. When calling a method you don't need to include `self` in the arguments as Python does it automatically.

instances of classes have attributes which can be accessed using **dot notation**. In `__init__` we can use `self.attribute` to assign values to attributes.

**Methods** can be added within a class using `def` like other functions. The methods can then be accessed using dot notation like attributes.

```Python
class Cat:
  def __init__(self, color, legs):
    self.color = color
    self.legs = legs

  def meow(self):
    print("meow!")

felix = Cat("ginger", 4)
felix.meow()
# meow!
```

**Class attributes** can be defined by assigning a variable inside a class. They can then be accessed from an instance or the class itself.

Trying to access an attribute that doesn't exist will result in an `AttributeError`

### **Inheritance**

Inheritance allows for sharing of functionality between classes. Classes used for shared class functionality are referred to as *superclasses*.

Inheriting classes are called *subclasses*. A subclasses methods or attributes will override those of the superclass if they share the same name.

`class Name(Superclass)` is used to assign superclasses to classes, as seen below:

```Python
#from sololearn
class Animal:
  def __init__(self, name, color):
    self.name = name
    self.color = color

class Cat(Animal):
  def purr(self):
    print("Purr...")

class Dog(Animal):
  def bark(self):
    print("Woof!")

fido = Dog("Fido", "brown")
print(fido.color)
fido.bark()

#fido inherited attributes from the Animal superclass!
```

Inheritance can be chained, which is called *indirect inheritance*.

`super` refers to the parent class and can be used to invoke methods from a superclass.

### **Magic Methods & Operator Overloading**

Magic methods are special methods surrounded with double underscores, like `__init__`. They are also known as **dunders**.

One use of dunders is **operator overloading** which defines operators for customer classes.

```Python
# from sololearn
class Vector2D:
  def __init__(self, x, y):
    self.x = x
    self.y = y
  def __add__(self, other):
    return Vector2D(self.x + other.x, self.y + other.y)

first = Vector2D(5, 7)
second = Vector2D(3, 9)
#__add__ redefines the + operator
result = first + second
print(result.x)
print(result.y)
```

Other **operator** magic methods are:

* `__sub__` for `-`
* `__mul__` for `*`
* `__truediv__` for `/`
* `__floordiv__` for `//`
* `__mod__` for `%`
* `__pow__` for `**`
* `__and__` for `&`
* `__xor__` for `^`
* `__or__` for `|`

`x + y` is translated to `x.__add__(y)`.

If `__add__` isn't implemented on x yet, the equivalent `r` method is called: `y.__radd__(x)`

Python also has **comparison magic methods**:

* `__lt__` for `<`
* `__le__` for `<=`
* `__eq__` for `==`
* `__ne__` for `!=`
* `__gt__` for `>`
* `__ge__` for `<=`

If `__ne__` is not implemented, it returns it's opposite of `__eq__`. there are no other relationships for comparison operators.

### **Object Lifecycle**

The object lifecycle goes `creation > manipulation > destruction`.

The first stage is the **definition** of a class, followed by **instantiation** when `__init__` is called.

`__new__` is called and memory is allocated for storing the instance.

An object is **destroyed** when it's reference count reaches zero. Upon destruction, allocated memory is freed up.

`del` is used to reduce the reference count of an object by one, often leading to deletion. `del` relates to the `__del__` magic method.

### **Data Hiding**

*Encapsulation* involves packaging related variables and functions into an instance of a class.

*Data Hiding* is a related concept, which states that implementation details of a class should be hidden.

Python's philosophy is "we are all consenting adults here", meaning private methods aren't restricted.

**Weakly private** methods and attributes are preceded by a **single underscore**. This is mostly a convention, and the only effect will be that `from module_name import *` won't import private variables.

**Strongly private** methods and attributes are preceded by a **double underscore**. 

Strongly private variabels have their name mangled, essentially including the class name. They can still be accessed by using `_Class__privatemethod`.

### **Class & Static Methods**

Class methods are called by a class and passed to the `cls` parameter fo a method.

Class methods are marked with a `@classmethod` decorator:

```Python
#From sololearn:
class Rectangle:
  def __init__(self, width, height):
    self.width = width
    self.height = height
  def calculate_area(self):
    return self.width * self.height
  @classmethod
  def new_square(cls, side_length):
    return cls(side_length, side_length)
  
square = Rectangle.new_square(5)
print(square.calculate_area()) 
```

A common use of class methods is as factory methods. They can instantiate an instance of a class with different parameters.

Static methods are similar, but don't receive additional arguments. They don't receive any additional arguments. They are identical to normal functions that belong to a class.

Static methods are marked with a `@staticmethod` decorator:

```Python
#from sololearn
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings

  @staticmethod
  def validate_topping(topping):
    if topping == "pineapple":
      raise ValueError("No pineapples!")
    else:
      return True
  
ingredients = ["cheese", "onions", "spam"]
if all(Pizza.validate_topping(i) for i in ingredients):
  pizza = Pizza(ingredients)
```

For reference:

* `self` - regular methods
* `cls` - classmethods
* Just args - staticmethods

### **Properties**

Properties provide a way fo customizing access to instance attributes.

They are created using the `@property` decorator. When accessed, a method marked in this way executes instead. This can be used to make a property read-only.

```Python
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings

  @property
  def pineapple_allowed(self):
    return False

pizza = Pizza(["cheese", "tomato"])
print(pizza.pineapple_allowed)
#Trying to assign will cause an AttributeError
pizza.pineapple_allowed = True
```

Properties can be set with **setter/getter** functions. As the name implies, setters set a properties value, and getters get the value.

To define a setter or getter, use a decorator of `@property.setter` or `@property.getter`.

### **A Simple Game**

Object-orientation is useful for managing different objects, such as in a game. Below is example code from sololearn of a simple game.

```Python
#from sololearn:
def get_input():
  command = input(": ").split()
  verb_word = command[0]
  if verb_word in verb_dict:
    verb = verb_dict[verb_word]
  else:
    print("Unknown verb {}".format(verb_word))
    return

  if len(command) >= 2:
    noun_word = command[1]
    print (verb(noun_word))
  else:
    print(verb("nothing"))

def say(noun):
  return 'You said "{}"'.format(noun)

verb_dict = {
  "say": say,
}

while True:
  get_input()
```

```Python
#from sololearn:
class GameObject:
  class_name = ""
  desc = ""
  objects = {}

  def __init__(self, name):
    self.name = name
    GameObject.objects[self.class_name] = self

  def get_desc(self):
    return self.class_name + "\n" + self.desc

class Goblin(GameObject):
  class_name = "goblin"
  desc = "A foul creature"

goblin = Goblin("Gobbly")

def examine(noun):
  if noun in GameObject.objects:
    return GameObject.objects[noun].get_desc()
  else:
    return "There is no {} here.".format(noun)

verb_dict = {
  "say": say,
  "examine": examine,
}
```

```Python
class Goblin(GameObject):
  def __init__(self, name):
    self.class_name = "goblin"
    self.health = 3
    self._desc = "A foul creature"
    super().__init__(name)

  @property
  def desc(self):
    if self.health >= 3:
      return self._desc
    elif self.health == 2:
      health_line = "It has a wound on its knee."
    elif self.health == 1:
      health_line = "Its left arm has been cut off!"
    elif self.health <= 0:
      health_line = "It is dead."
    return self._desc + "\n" + health_line

  @desc.setter
  def desc(self, value):
    self._desc = value

def hit(noun):
  if noun in GameObject.objects:
    thing = GameObject.objects[noun]
    if type(thing) == Goblin:
      thing.health = thing.health - 1
      if thing.health <= 0:
        msg = "You killed the goblin!
      else:
        msg = "You hit the {}".format(thing.class_name)
  else:
    msg = "There is no {} here.".format(noun)
  return msg
```

Neat!

## **Regular Expressions**
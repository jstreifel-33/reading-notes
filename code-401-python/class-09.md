# Dunder Methods and Statistics

## Dunder Methods

[Source: Blog Post - Enriching Your Python Classes With Dunder (Magic, Special) Methods](https://dbader.org/blog/python-dunder-methods)

Dunder methods are methods wrapped in double underscores, such as `__init__`.

Dunders can be used to emulate built in types. `__len__` can be used to define the return from len(obj), or `__str__` can be used to define what an object looks like as a string.

### Dunders and Types

* `__init__` - run upon object instantiation using a class. Often used for initialization of object properties, allowing for creation of unique objects.
* `__repr__` - string representation of an object, showing how the object is made ex: `"Account(owner, amount)`
* `__str__` - nice string representation of object. This is to explain to the end user what the object is.
* `__len__` & `__getitem__` can be used to make an object iterable. `__len__` returns what is effectively the length of the iterable object and `__getitem__` determines the return for each index.

### Operator Overloading

Dunders can be used to define what happens when an operator is called on an object.

Refer to github notes for more on magic operator overloading: [Python101 - Magic Methods & Operator Oberloading](https://github.com/jstreifel-33/reading-notes/blob/gh-pages/code-401-python/pre-work/python101.md#magic-methods--operator-overloading)

### Callable Python Objects

The `__call__` dunder makes an object callable like a function. This can define what behavior or operations you want when "invoking" an object after instantiation.

## An Intro to Statistics

[Source: Tutorial - Basic Statistics in Python - Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)

**Probability**, at it's most basic level asks the question "what is the chance of an event happening?"

An **event** is an outcome of interest. Think flipping a coin. Heads and tails are events in that case.

**Sample Space** refers to the set of all possible events in a scenario.

Probability can be calculated by taking the number of times an event can happen, and dividing it by the sample space.

Typically, as sample size increases, deviation from the probability of an event will decrease. Using Python, we can *model* events and simulate them many times to get a more accurate idea of event probability.

### Data and distribution

**Normal distribution** refers to when data falls in a symmetrical bell curve. In a normal distribution, the highest point represents the event with the highest probability of occurring.

The **central limit theorem** states that if many estimates are taken of a trial, the distribution of the estimates will look like a normal distribution. It also states that the highest point of the distribution will approach the mean probability.

The **Three Sigma Rule** is an expression of how observations fall within a normal distribution. It states that 68% will fall within 1 stdev (sigma), 95% within 2 stdev, and 99.7% within 3 stdev.

**Z-score** is used to answer the question of how many standard deviations from the mean a given data point is. `z = (x_i - mean)/(stdev)`. These are typically used with a **z-table**.
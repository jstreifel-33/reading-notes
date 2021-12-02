# Classes, Objects, Recursive Thinking, and Pytest

## Classes and Objects

[Source: learnpython.org - Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)

In Python, objects are an encapsulation of variables and functions, provided by classes.

Classes are templates for objects.

```Python
class Dog:
    legs: 4

    def speak(self):
        print("Woof!")

lassie = Dog()
```

Creating an object from a class is as simple as invoking the class, and assigning the created object to a variable (lassie above contains an object of class Dog).

Object variables and functions are accessed using dot notation:

```Python
lassie = Dog()

print(lassie.legs)
#4

lassie.speak()
#"Woof!"
```

To assign values to class, the `__init__()` function is necessary:

```Python
class Dog:
    def __init__(self, breed):
        self.breed = breed

    legs: 4

    def speak(self):
        print("Woof!")


lassie = Dog("Retriever")

print(lassie.breed)
#"Retriever"
```

## Thinking Recursively

[Source: Real Python - Thinking Recursively in Python](https://realpython.com/python-thinking-recursively/)

### Maintaining State in Recursion

Each recursive call has it's own unique context. There are two ways to maintain state as a result:

* Thread the state through each recursive call
* Keep the stat in global scope

```Python
#Threading (from realpython.org):

def sum_recursive(current_number, accumulated_sum):
    if current_number == 11:
        return accumulated_sum
    
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)
```

```Python
#Global mutable state(from realpython.org):

current_number = 1
accumulated_number = 0


def sum_recursive():
    global current_number
    global accumulated_sum

    if current_number == 11:
        return accumulated_sum

    else:
        accumulated_sum = accumulated_sum + current_number
        current_number = current_number + 1
        return sum_recursive()
```

### Recursive Data Structures

A recursive data structure is any data structure that can be generated recursively.

```Python
#lists are recursive, thanks to the attach_head() function

attach_head(1,
            attach_head(2,
                        attach_head(3, [])))
```

Other recursive data types include sets, trees, and dictionaries.

Recursive functions can often have their structure informed by the data type that they accept as input!

# Naive Recursion and Caching results

Following recursion execution can sometimes reveal that recursive functions are severely inefficient. This is true of the classic Fibonacci recursive function:

```Python
def fibonacci(n):
    print("Calculating F", "(", n, ")", sep="", end=", ")

    if n == 0:
        return 0
    elif n == 1:
        return 1

    else:
        return fibonacci(n-1) + fibonacci(n-2)
```

This function can be improved with caching using the functools library's `lru_cache` decorator!

```Python
#from realpython.com:

from functools import lru_cache

@lru_cache(maxsize=None)
def fibonacci(n):
    print("Calculating F", "(", n, ")", sep="", end=", ")

    if n == 0:
        return 0
    elif n == 1:
        return 1

    else:
        return fibonacci(n-1) + fibonacci(n-2)
```

## Pytest Fixtures and Coverage

[Source: Linux Journal - Python Testing with pytest: Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)

### Fixtures

Fixtures in pytest are created by combining the `pytest.fixture` decorator with a function definition.

The reading example deals with a case where a function to be tested reverses lines:

```Python
#From linuxjournal.com

def reverse_lines(f):
    return [one_line.rstrip() + '\n' 
            for one_line in f]
```

To test this function, you must pass it a file-like object. Creating that inside the test would be a pain, so we can use a pytest fixture instead:

```Python
#From linuxjournal.com

@pytest.fixture
def simple_file():
    return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))
```

The function name of your fixture can then be passed to test, to use the return value as an argument!

```Python
#From linuxjournal.com

def test_reverse_lines(simple_file):
    assert reverse_lines(simple_file) == ['cba\n', 'fed\n', 
    'ihg\n', 'lkj\n']
```

`@pytest.fixture(scope='module')` will set a module to only run once per test, making it's output value available in all following tests.

### Coverage

Coverage is a description of how thoroughly code is tested.

The `pytest-cov` package from PyPI is a great tool for generating coverage report.

When installed, invoking `pytest --cov` will generate a coverage report for every library used by your program. `pytest --cov=library` can be used to narrow down the report.

`coverage HTML` will convert the report to something readable for human eyes.

Neat!
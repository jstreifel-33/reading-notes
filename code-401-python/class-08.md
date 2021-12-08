# List Comprehension

[Source: List Comprehension in Python](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

List comprehensions are a tool for creating lists in a concise expression. They allow for simple manipulation of all items in a list.

## Syntax

`my_new_list = [*expression* for *item* in *list*]

A python list comprehension requires 3 ingredients:

1. The expression to carry out (*expression*)
2. The object to perform the expression on (*item*)
3. An iterable list of objects to build from (*list*)

## Creating lists

List comprehensions can be used with the range() function.

Per the reading, something that would normally be accomplished with loops...

```Python
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
#[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

...can be rewritten with a list comprehension:

```Python
squares = [x**2 for x in range(10)]

print(squares)
#[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

## Functions and if statements

An if statement can be used at the end of a list comprehension, to act as a filter for the expression.

From the reading:

```Python
even_numbers = [ x for x in range(1,20) if x % 2 == 0]

print(even_numbers)
#[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

Functions can also be called within the expression of a list comprehension. The return of the function is what will be placed in the output array.

From the reading:

```Python
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
#[2, 4, 6, 8, 10, 12, 14, 16, 18]
```

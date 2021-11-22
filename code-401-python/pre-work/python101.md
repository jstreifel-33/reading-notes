# How to Python

## Basic Concepts

## Strings & Variables

## Control Structures

### List Functions

* `List.append(value)` - adds a value to the end of an existing list. Returns none
* `len(list)` - returns the **length** of a list
* `List.insert(index, value)` - inserts `value` at any specified position in a list
* `List.index(value)` - finds the first occurrence of a `value` and returns its index
* `max(list)` `min(list)` - returns the highest or lowest value in a list
* `list.count(item)` - returns count of how many times `item` occurs in a list
* `list.remove(item)` - removes an object from a list
* `list.reverse()` - reverses the items in a list

### `while` Loops

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

### `for` Loops

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

### Range

* `range(num)` returns a sequence of numbers.
* By default, it starts from 0 and stops **before** the specified number.
* `range(start, stop)` - A second argument can be included to change the start point. The start number **will** be included in the range, while the stop number **will not** be included in the range.
* `range(start, stop, step)` - A third argument can be included to determine the **interval** that steps increase by.
  * `range(20, 5, -2)` - A **negative step value** can be used to generate a range of decreasing numbers.

## Functions and Modules

### Code Reuse



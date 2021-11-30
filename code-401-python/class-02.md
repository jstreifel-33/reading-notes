# Testing and Modules

## Test-Driven Development

[Source: In Tests We Trust - TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

**Unit tests** are pieces of code to exercise the behavior of your code.

**Test-Driven Development** (TDD) involves thinking of and writing tests *before* writing code.

```Python
#Sameple test from reading to test gender detection based on name
def
test_should_return_female_when_the_name_if_from_female_gender():

  detector = GenderDetector()

  expected_gender = detector.run('Ana')

  assert expected_gender == 'female'
```

Important aspects of a unit test:

* **Test Name** - names should be descriptive about what is being tested.
* **File Name** - This should match the name of the module being tested. Standard convention is `test_module.py`.
* **AAA** - Arrange, Act, Assert
  * *Arrange* - organize the data needed to execute the code (input)
  * *Act* - execute code under test (behavior)
  * *Assert* - check if the result matches expectations (output)

TDD is a 3 step process:

1) write a unit test
2) write a feature that passes your test
3) refactor the passing code

When working in TDD, take the smallest steps possible: write a test - get your code to pass - write the next test - add to your code to pass again - repeat until done.

TDD leads to more reliable code. If updates are ever necessary, you can run your tests to ensure everything still works as expected.

## If name equals main

[Source: GeeksforGeeks - What does the if__name__=="__main__": do?](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)

`if__name__=="__main__":` can be used to separate module code and script code.

When the python interpreter runs a source file one of the first things it does is set the `__name__` variable to have a value of "__main__".

HOWEVER, if the file is being imported, `__name__` will be set to the module's name.

This distinction allows to include two separate sections of code in one python file: **code to run when the file is executed** and **code to run when the file is imported**.

Using `if__name__=="__main__":` we can set up python modules that can be tested alone in the interpreter, by setting up inputs or dependencies manually when the file is executed as main.

## Recursion

[Source: GeeksforGeeks - Recursion](https://www.geeksforgeeks.org/recursion/)

Recursion a process in which a function calls itself either directly or indirectly.

Recursive programming requires the identification of a **base case**. This is the point at which recursion will end, and a function will resolve it's recursive calls. In cases where a base case cannot be reached, we will encounter a *stack overflow*. This happens when memory in a system is exhausted by recursive executions.

**Direct recursion** is when a function calls itself inside it's own execution.

**Indirect recursion** is when a function calls some other function that eventually calls the original function again, creating a recursive loop.

Recursive programs can often be written as iterative programs and vice versa. It's important to note that recursive programs are more memory intensive.

That said, some problems are inherently recursive. In such cases, recursive code is preferred for ease of understanding.
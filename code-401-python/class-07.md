# Python Scope

Python is a dynamically-typed language, so variables come into existence when you assign them.

Python scope determines where names are visible within code. Scopes are implemented as dictionaries called **namespaces**, which are stored in the `.__dict__` attribute.

## LEGB

* Local (function) scope - the code block body of any function or lambda expression.
* Enclosing (or nonlocal) scope - special scope that only exists in nested functions.
* Global (module) scope - top-most scope in a Python program, script, or module
* Built-in scope - special python scope that's created whenever you run a script or open a session.

## Modifying scope behavior

Two keywords can be used to modify the content of global and nonlocal  names:

1. `global`
2. `nonlocal`

### The `global` Statement

Trying to reassign a global variable inside of a local scope will create a new local variable with that name.

To get around this, `global` can be placed before a variable. `global` will map any following names (separated by commas) to their global variable counterparts.

The use of `global` is considered bad practice in general. Usually, if you're using global a lot there can be a better way to write your code.

### The `nonlocal` Statement

`nonlocal` is similar to `global` but on a nested function scale. Inside of a nested function, the `nonlocal` statement can be used to make a name available in parent functions.

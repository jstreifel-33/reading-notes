# File IO & Exceptions

## Read & Write Files

[Source: Real Python - Reading and Writing Files in Python](https://realpython.com/read-write-files-python/)

A file is composed of 3 parts:

1. **Header** - metadata such as file name, size, type, etc.
2. **Data** - contents of the file as written
3. **End of file (EOF)** - special character indicating the end of the file

End of lines in a file can follow one of two conventions:

1. CR+LF (/r/n) - standard set by American Standards Association (ASA). Used by windows
2. LF (/n) - standard set by International Organization for Standardization (ISO). Used by Unix and newer Mac versions

**side-note**: *of course* the ASA had to be different. Leave it to the country that insists on sticking to [made up units from the 1800's](https://en.wikipedia.org/wiki/United_States_customary_units). Why we don't universally adopt ISO standards and SI units is beyond me. Meanwhile, the metric system is making a push to [redefine measurements based on **universal constants**](https://www.nist.gov/si-redefinition) like the speed of light and the Planck constant because *science exists*.

Direct quote from the reading:

>This can make iterating over each line problematic, and you may need to account for situations like this.

*It doesn't have to be like this.*

Ok. Back to the matter at hand.

**Character encoding** is also important to pay attention to. ASCII is a subset of UNICODE and the two are the most common encodings. If Parsing UNICODE as ASCII, you will likely throw an error.

`open(filepath)` is used open files in Python. They can then be processed.

There are two ways to use `open()`:

```Python
# The first way assigns the opened file. 
# try/finally is used to ensure the file is closed when done.
f = open('some_file.txt')
try:
    #do things with f
finally:
    f.close()

# The second way is to use with.
# when the code inside of a with statement
# completes, the file will be closed automatically
with open('some_file.txt') as f:
    #do things with f
```

`.read(size=n)` will read n bytes from the file. size=-1 will read the entire file.

`.readlines()` will read the remaining lines and return them as a list.

`.write(string)` writes a string to file

`.writelines(sequence)` writes the sequence to file. *No line endings are appended automatically.*

## Exceptions in Python

[Source: Python Exceptions: An Introduction](https://realpython.com/python-exceptions/)

Exception errors occur when syntactically correct Python encounters an error during execution. Python has several built-in exceptions that can describe what went wrong.

`raise` can also be used to manually throw an exception, with a custom message.

```Python
x = 'foo'
if x != 'bar'
    raise Exception('invalid x value, expected "bar"')
```

Exceptions can be handled using `try...except` blocks. If an exception is encountered in try, teh associated except block will execute. This can offer the chance to create contingency code in the case of an error during execution.

If an exception is caught by a `try/except` block, the code will continue on as expected, provided we don't manually raise an exception.

`else` can be used after `try/except` to specify code to run in the case that *no exceptions are encountered*. This can be used for a success confirmation or code that depends critically on the code inside of `try`.

`finally` runs no matter what. Often used for cleanup, this will come after `try/except` and `else`.

```Python
try:
    # attempt to execute code
except:
    # execute this code if an exception happens
else:
    # execute this code if an exception doesn't happen
finally:
    # execute this code regardless
```

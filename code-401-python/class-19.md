# Automation in Python

## Regex

[Source: Datacamp - Python Regular Expression Tutorial](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)

Regex is used for detecting patterns. In Python, this will involve importing the `re` library.

Defining regex patterns in Python is done with a raw string literal, such as `r"potato"`.

Numbers and letters are the most simple characters that can be searched with regex, but there are others!

* `.` - Any single character except newline
* `^` - matches the start of the string
* `$` - end of the string
* `[abc]` - matches a b or c
* `\` - does a lot
  * if followed by a recognized escape character, the special meaning is taken
  * else if followed by a non escape character, treated like a normal character
  * else, if followed by metacharacter, removes special meaning.
* `\w` and `\W` - single letter, digit or underscore, OR not that, respectively
* `\s` and `\S` - whitespace and not that, respectively
* `\d` and `\D` - digit and not digit

There are many more. Check the reading or [regex101](https://regex101.com/) for more.

## Shutil

[Source: pymotw.com - shutil](https://pymotw.com/3/shutil/)

`shutil` is high-level file operation library for things like copying and archiving.

`copyfile()` copies the contents of a source to a destination.

`copy()` also copies, but interprets the output name like unix cp.

File metadata can be copied and transferred using `copymode()` and `copystat()`

`copytree()` can be used to copy entire directory trees. The destination directory must not exist before executing.

`which()` scans a path looking for a named file. If no match is found, returns None.

`make_archive()` creates a new archive file. Defaults to current directory, and executes recursively for all contents. `root_dir` and `base_dir` arguments can be used to change behavior.

`unpack_archive()` is used to extract files from an archive file.

`disk_usage()` returns a tuple with total space, amount in use, and amount remaining free.

All of these useful functions and methods can be used to manipulate and automate file operations on our machine!

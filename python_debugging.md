# Debugging in Python

## Common Errors in Python

### Indentation Errors

Indentation errors are common when writing Python code. Due to Python's dependence on indentation, it is very easy to make a mistake when writing code. Python DOES distinguish between indentation and spacing, so you must choose one or the other. Most IDE's will tell you if you have an indentation error.

Example:

```python
if True:
print("Hello")
else:
    print("Goodbye")
```

Console:

```none
  File "main.py", line 2
    print("Hello")
    ^
IndentationError: expected an indented block
```

Fix:

```python
if True:
    print("Hello")
else:
    print("Goodbye")
```

### Syntax Errors

Forgetting colons (:), commas (,) or parentheses are common errors.
Example:

```python
if True
    print("Hello"
else:
    print("Goodbye", "Goodbye again", "Goodbye again v2" sep="\n")
```

Console:

```none
  File "main.py", line 1
    if True
          ^
SyntaxError: invalid syntax
```

Fix:

```python
if True:
    print("Hello"
else:
    print("Goodbye", "Goodbye again", "Goodbye again v2" sep="\n")
```

Console:

```none
  File "main.py", line 3
    else:
    ^
SyntaxError: invalid syntax
```

Fix:

```python
if True:
    print("Hello"
else:
    print("Goodbye", "Goodbye again", "Goodbye again v2" sep="\n")
```

Console:

```none
Hello
```

There is another error in this snippet, but since the code is unreachable, it will not be found by the interpreter.
If we change that `True` to `False`, the code will be found and executed.
Change:

```python
if False:
    print("Hello")
else:
    print("Goodbye", "Goodbye again", "Goodbye again v2" sep="\n")
```

Console:

```none
  File "main.py", line 4
    print("Goodbye", "Goodbye again", "Goodbye again v2" sep="\n")
                                                         ^
SyntaxError: invalid syntax
```

Fix:

```python
if False:
    print("Hello")
else:
    print("Goodbye", "Goodbye again", "Goodbye again v2", sep="\n")
```

Console:

```none
Goodbye
Goodbye again
Goodbye again v2
```

#### Note: `\n` is a special character that is used to represent a newline character.

### Logical Errors

Logical errors are common when writing Python code. These errors are hardest to find, since they do not cause any Runtime errors in the console. These errors are usually caused by a mis-aligned line of code, or the wrong operator being used.

Example:

```python
sum_squares = 0
for i in range(10):
    i_sq = i**2
sum_squares += i_sq
print(sum_squares)
```

Console:

```none
81
```

This is only 9 squared, not the sum of the squares of 0 through 9.
Fix:

```python
sum_squares = 0
for i in range(10):
    i_sq = i**2
    sum_squares += i_sq
print(sum_squares)
```

Console:

```none
285
```

### Type Errors
Type errors occur when you try to perform an operation on a variable that is not the same type as the variable you are trying to perform the operation on.
The standard types go as follows:
- number (integer, float)
- string
- boolean
- list
- tuple
- dictionary
- set

Example:
```python
a = 1
b = "2"
c = a + b
print(c)
```
Console:
```none
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    c = a + b
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
Fix:
```python
a = 1
b = "2"
c = int(a) + int(b)
print(c)
```
Console:
```none
3
```
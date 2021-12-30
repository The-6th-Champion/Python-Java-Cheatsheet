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
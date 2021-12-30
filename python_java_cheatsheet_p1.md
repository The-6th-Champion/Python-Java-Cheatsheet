# Cheatsheet for Python and Java
## How to use this cheatsheet
This cheatsheet will show code snippets for certain ideas and tasks in Java, and then how you would go about doing them in Python. Certain Python concepts and functions will also be explained in more depth.

## Hello World
```java
public class Program {

    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
This is a simple program that prints out the string "Hello World!"
```python
print("Hello World!")
```

The print function is a built-in function in Python. It prints out the string that is passed to it. This is compared to System.out.println in Java.
Python is not naturally object oriented, so the need for a main function and a class is not necessary.

## Variables
```java
public class Program {

    public static void main(String[] args) {
        int x = 5;
        double y = 10d;
        double z = x + y;
        boolean a = true;
        String b = "Hello World!";
        System.out.println(z);
        System.out.println(a);
        System.out.println(b);
    }
}
```
This is a program that prints out the values of the variables z, a, and b. To make variables, you first use a keyword or type of data, then a name for the variable, an =, and then a value. In python, you do the same, but without specifying type
```python
x = 5
y = 10.0
z = x + y
a = True
b = "Hello World!"
print(z)
print(a)
print(b)
```
additionally, `float`s are used instead of `double`s in python.
### Note
Python 3 has the ability to type annotate, or give 'soft' types to variables. An example is shown below. Python is dynamically typed by nature, but annotations allow for better understanding of code.
```python
x: int = 5
y: float = 10.0
z: float = x + y
a: bool = True
b: str = "Hello World!"
print(z)
print(a)
print(b)
```

## Conditionals

### Conditional Statements
```java
public class Program {

    public static void main(String[] args) {
        int x = 5;
        if (x > 10) {
            System.out.println("x is greater than 10");
        } else if (x < 10) {
            System.out.println("x is less than 10");
        } else {
            System.out.println("x is equal to 10");
        }
    }
}
```
This is a program that prints out the string "x is greater than 10" if x is greater than 10, "x is less than 10" if x is less than 10, and "x is equal to 10" if x is equal to 10. Conditionals in Python are similar, but with a few syntax differences.
```python
x = 5
if x > 10:
    print("x is greater than 10")
elif x < 10:
    print("x is less than 10")
else:
    print("x is equal to 10")
```
Note that the elif keyword is used instead of else if.
Additionally, the indentation of the code is important. If you indent the code incorrectly, Python will not interpret it correctly. This is due to how Python uses colons instead of curly braces.

### Logical Operators
```java
public class Program {

    public static void main(String[] args) {
        int x = 5;
        // && is the logical AND operator
        if (x > 10 && x < 20) {
            System.out.println("x is between 10 and 20");
        }
        // || is the logical OR operator
        if (x > 10 || x < 20) {
            System.out.println("x is between 10 and 20");
        }
        // ! is the logical NOT operator
        if (!(x > 10)) {
            System.out.println("x is not greater than 10");
        }
    }
}
```
This is a program that prints out the string "x is between 10 and 20" if x is between 10 and 20, "x is between 10 and 20" if x is between 10 and 20, and "x is not greater than 10" if x is not greater than 10. Python has the same logical operators as Java, but with a few differences.
```python
x = 5
if x > 10 and x < 20:
    print("x is between 10 and 20")
if x > 10 or x < 20:
    print("x is between 10 and 20")
if not x > 10:
    print("x is not greater than 10")
```
Python uses the keywords `and` and `or` instead of `&&` and `||`. The same goes for `not` (or `!`).

Java and Python share the same operators for comparison.
```java
public class Program {

    public static void main(String[] args) {
        int x = 5;
        if (x == 5) {
            System.out.println("x is equal to 5");
        }
        if (x != 5) {
            System.out.println("x is not equal to 5");
        }
        if (x > 5) {
            System.out.println("x is greater than 5");
        }
        if (x >= 5) {
            System.out.println("x is greater than or equal to 5");
        }
        if (x < 5) {
            System.out.println("x is less than 5");
        }
        if (x <= 5) {
            System.out.println("x is less than or equal to 5");
        }
    }
}
```
This is a program that prints out the string "x is equal to 5" if x is equal to 5, "x is not equal to 5" if x is not equal to 5, "x is greater than 5" if x is greater than 5, "x is greater than or equal to 5" if x is greater than or equal to 5, "x is less than 5" if x is less than 5, and "x is less than or equal to 5" if x is less than or equal to 5.
```python
x = 5
if x == 5:
    print("x is equal to 5")
if x != 5:
    print("x is not equal to 5")
if x > 5:
    print("x is greater than 5")
if x >= 5:
    print("x is greater than or equal to 5")
if x < 5:
    print("x is less than 5")
if x <= 5:
    print("x is less than or equal to 5")
```

### Switch Statements
```java
public class Program {

    public static void main(String[] args) {
        int x = 5;
        switch (x) {
            case 1:
                System.out.println("x is equal to 1");
                break;
            case 2:
                System.out.println("x is equal to 2");
                break;
            case 3:
                System.out.println("x is equal to 3");
                break;
            default:
                System.out.println("x is not equal to 1, 2, or 3");
        }
    }
}
```
Python does not have switch statements. Instead, you can use if statements to check for specific values.
```python
x = 5
if x == 1:
    print("x is equal to 1")
elif x == 2:
    print("x is equal to 2")
elif x == 3:
    print("x is equal to 3")
else:
    print("x is not equal to 1, 2, or 3")
```

## Collections
### Java Arrays and Python Tuples
```java
public class Program {

    public static void main(String[] args) {
        int[] x = {1, 2, 3, 4, 5};
        System.out.println(x[0]);
        System.out.println(x[1]);
        System.out.println(x[2]);
        System.out.println(x[3]);
        System.out.println(x[4]);
    }
}
```
This is a program that prints out the values of the array.
```python
x: tuple = (1, 2, 3, 4, 5)
print(x[0])
print(x[1])
print(x[2])
print(x[3])
print(x[4])
```
A tuple is a collection which is ordered and unchangeable. In Python tuples are written with round brackets. These are similar to arrays in Java.
Tuples are immutable, meaning that they cannot be changed. They can have different types, but they cannot be changed.
### Java Array Lists and Python Lists
```java
public class Program {

    public static void main(String[] args) {
        ArrayList<Integer> x = new ArrayList<Integer>();
        x.add(1);
        x.add(2);
        x.add(3);
        x.add(4);
        x.add(5);
        System.out.println(x.get(0));
        System.out.println(x.get(1));
        System.out.println(x.get(2));
        System.out.println(x.get(3));
        System.out.println(x.get(4));
    }
}
```
This is a program that prints out the values of the arrayList.
```python
x: list = [1, 2, 3, 4, 5]
print(x[0])
print(x[1])
print(x[2])
print(x[3])
print(x[4])
```
A list is a collection which is ordered and changeable. In Python lists are written with square brackets. These are similar to ArrayLists in Java.
Lists are mutable, meaning that they can be changed. They can have different types, but they can be changed.

### Python Dictionaries
```python
x: dict = {
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
print(x["key1"])
print(x["key2"])
print(x["key3"])
# Ouputs:
# value1
# value2
# value3
```
A dictionary is a collection which is unordered, changeable and not indexed. In Python dictionaries are written with curly brackets, and they have keys and values. Java has a similar data type.

### Python Sets
```python
x: set = {1, 2, 3, 4, 5}
print(x)
# Ouputs:
# {1, 2, 3, 4, 5}
```
A set is a collection which is unordered and unindexed. In Python sets are written with curly brackets, and they have values. Java has a similar data type. You cannot access items in a set by referring to an index, since sets are unordered the items has no index.

### Python len() 
```python
# List length
x: list = [1, 2, 3, 4, 5]
print(len(x))
# Tuple length
x: tuple = (1, 2, 3, 4, 5)
print(len(x))
# Set length
x: set = {1, 2, 3, 4, 5}
print(len(x))
# Dictionary length
x: dict = {
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
print(len(x))
# String length
x: str = "Hello World"
print(len(x))


# Output:
# 5
# 5
# 5
# 3
# 11
```
the len() function returns the length of a string, a list, a tuple, a set, or a dictionary (in essence, any iterable). Java has seperate methods for each type but Python just has the universal len() function.


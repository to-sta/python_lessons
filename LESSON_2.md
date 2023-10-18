#  Lesson  2 - Comments, Variables, Data Types and Operators

1. Comments
2. Variables
3. Data Types
4. Operators
5. Exercises

## 1. Comments
Comments provide a way for you to annotate your code. They do not affect the operation of the program and are included to ensure that you or anyone maintaining your code understands its functionality.

There are two types of comments available: single-line and multi-line comments. Single-line comments start with `#`. Everything that follows `#` on the same line is considered a comment.

```python
# This is a single line comment

variable = 5 # Comment after code
```

Multi-line comments can be written using triple quotes. You can use either single quotes `'''` or double quotes `"""` to start and end the comment. Everything within these quotes is considered a comment

```python
"""
This is a multiline comment.
It can span multiple lines.
"""

'''
This is also a 
multi-line comment. 
'''
```

> [!NOTE]
> It’s important to note that these multi-line comments are actually strings, but since they are not assigned to any variable, they are ignored by the interpreter. 

## 2. Variables
Python **variables** are containers for storing data values. To create a **variable**, you assign it a value and then start using it. Assignment is done with a single equals sign **(=)**. A **variable** refers to a memory address (e.g., 0x7ff87bd3e388) where data is stored.

There are **several rules** regarding variable naming that we have to follow:

* A variable name must start with a letter or the underscore character.
* A variable name cannot start with a number.
* A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _).
* Variable names are case-sensitive (name, Name, and NAME are three different variables).
* A variable name cannot be any of the Python keywords (e.g., if, else, class, def, int, ...).

The part to the left of the assignment operator is the variable name, and the right side is its value.

```python
variable_name = 4
```
Here are a few examples of **valid** and **invalid** variable names:

```python
# Valid variable names:
myvariable = "John"
my_variable = "John"
_myvariable = "John"
myVariable = "John"
MYVARIABLE = "John"
myvariable2 = "John"

# Illegal variable names:
2myvariable = "John"
my-variable = "John"
my var = "John"
```

It is also possible to assign multiple variables in one line:

```python
name, age = "Max", 18
```


Python is **dynamically typed**, which means that variable types are determined and checked at runtime. We can reassign variables without worrying about the change of data type. Reassigning a variable will overwrite its value:

```python
variable = 4
print(variable) # Outputs: 4
variable = "max"
print(variable) # Outputs: max
```

> [!NOTE]
> Variable names should be in **lowercase**, with **words separated by underscores** as necessary to improve readability. This is also known as **"snake case"**. 
>
> You might be wondering why you would want to start a variable name with an **"_"**. This can be beneficial when there are **reserved keywords** like **"class"**. This reserved keyword could also make sense in the context of parsing CSS classes; then we would create a variable _class. 
>
> For more information about naming conventions regarding functions, refer to the [PEP 8 style guide](https://peps.python.org/pep-0008/#function-and-variable-names).

## 3. Data Types

**Python** comes with a variety of built-in data types. Let's start with the fundamentals, which can be grouped into categories:

* Numeric data types
* String data types
* Boolean data types

<ins>Numeric data types:</ins>
There are two fundamental numeric data types: the `int` data type to represent integer numbers and the `float` data type to represent floating-point numbers.

<ins>String data type:</ins>
A string is a collection of one or more characters enclosed in single quotes, double quotes, or triple quotes. The corresponding data type in Python is called **"str"**.

<ins>Boolean data type:</ins>
The boolean value can be either `True` or `False`. Numerically, True is equal to **1** and False is equal to **0**. The corresponding data type in Python is called **"bool"**.

We can use the built-in function `type()` to determine the data type of a variable or value. For example, calling `type(5)` would return `<class 'int'>`.

```python
print(type(4))                   # Outputs: <class 'int'>
print(type(3.14))                # Outputs: <class 'float'>
print(type("Hello World"))       # Outputs: <class 'str'>
print(type(True))                # Outputs: <class 'bool'>
```

We can create these datatypes by simply assigning them to a variable or using a **constructor** function. For example, if we want to convert a numeric data type to a string, we can use the string constructor:

```python
variable = 2
print(type(variable))            # Outputs: <class 'int'>
variable = str(variable)
print(type(variable))            # Outputs: <class 'str'>
```

There are constructor functions for all built-in data types (e.g., `bool()`, `int()`, `float()`).

> [!NOTE]
> There are more built-in data types than those mentioned above (e.g., **complex numbers** have a numeric data type called **complex**). Also, data structures are considered as data types, but we will address them later on.

## 4. Operators
Operators are used to perform specific operations on variables and values. Python comes with a variety of operators that can be grouped into categories:

* Arithmetic operators
* Assignment operators
* Comparison operators
* Logical operators
* Identity operators
* Membership operators
* Bitwise operators

Don't worry, we won't use all of them. This list is only for completeness. In the exercise portion of this lesson, we will focus on the most common operators. 

Let's go through them one by one.

<ins>Arithmetic operators</ins>

Arithmetic operators in Python are used to perform mathematical operations on values.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Name</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>+</td>
        <td>Addition</td>
        <td style="text-align: center">x + y</td>
    </tr>
    <tr>
        <td>-</td>
        <td>Subtraction</td>
        <td style="text-align: center">x - y</td>
    </tr>
    <tr>
        <td>*</td>
        <td>Multiplication</td>
        <td style="text-align: center">x * y</td>
    </tr>
    <tr>
        <td>/</td>
        <td>Division</td>
        <td style="text-align: center">x / y</td>
    </tr>
    <tr>
        <td>%</td>
        <td>Modulus</td>
        <td style="text-align: center">x % y</td>
    </tr>
    <tr>
        <td>**</td>
        <td>Exponentation</td>
        <td style="text-align: center">x ** y</td>
    </tr>
    <tr>
        <td>//</td>
        <td>Floor division</td>
        <td style="text-align: center">x // y</td>
    </tr>
</table>

<ins>Assignment operators</ins>

These are used to assign values to variables. The basic assignment operator is =, but there are others which combine arithmetic operations with assignment.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th style="text-align: center">Example</th>
        <th style="text-align: center">Equivalent Expression</th>
    </tr>
    <tr>
        <td>=</td>
        <td style="text-align: center">x = 5</td>
        <td style="text-align: center">-</td>
    </tr>
    <tr>
        <td>+=</td>
        <td style="text-align: center">x += 5</td>
        <td style="text-align: center">x = x + 5</td>
    </tr>
    <tr>
        <td>-=</td>
        <td style="text-align: center">x -= 5</td>
        <td style="text-align: center">x = x - 5</td>
    </tr>
    <tr>
        <td>/=</td>
        <td style="text-align: center">x /= 5</td>
        <td style="text-align: center">x = x / 5</td>
    </tr>
    <tr>
        <td>%=</td>
        <td style="text-align: center">x %= 5</td>
        <td style="text-align: center">x = x % 5</td>
    </tr>
    <tr>
        <td>//=</td>
        <td style="text-align: center">x //= 5</td>
        <td style="text-align: center">x = x // 5</td>
    </tr>
    <tr>
        <td>^=</td>
        <td style="text-align: center">x ^= 5</td>
        <td style="text-align: center">x  = x ^ 5</td>
    </tr>
    <tr>
        <td>>>=</td>
        <td style="text-align: center">x >>= 5</td>
        <td style="text-align: center">x  =  x >>  5</td>
    </tr>
    <tr>
        <td><<=</td>
        <td style="text-align: center">x <<= 5</td>
        <td style="text-align: center">x  =  x << 5</td>
    </tr>
</table>

<ins>Comparison operators</ins>

Comparsion operators are used to evaluate a statment and they will return `True` or `False`.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Name</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>==</td>
        <td>Equal</td>
        <td style="text-align: center">x == y</td>
    </tr>
    <tr>
        <td>!=</td>
        <td>Not equal</td>
        <td style="text-align: center">x - y</td>
    </tr>
    <tr>
        <td>></td>
        <td>Greater than</td>
        <td style="text-align: center">x > y</td>
    </tr>
    <tr>
        <td><</td>
        <td>Less than</td>
        <td style="text-align: center">x < y</td>
    </tr>
    <tr>
        <td>>=</td>
        <td>Greater than or equal to</td>
        <td style="text-align: center">x >= y</td>
    </tr>
    <tr>
        <td><=</td>
        <td>Less than or equal to</td>
        <td style="text-align: center">x ** y</td>
    </tr>
</table>

<ins>Logical operators</ins>

These are used to combine conditional statements. 

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Description</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>and</td>
        <td>Returns True if both statements are true</td>
        <td style="text-align: center">x < 5 and  x < 10</td>
    </tr>
    <tr>
        <td>or</td>
        <td>Returns True if one of the statements is true</td>
        <td style="text-align: center">x < 5 or x < 4</td>
    </tr>
    <tr>
        <td>not</td>
        <td>Reverse the result, returns False if the result is true</td>
        <td style="text-align: center">not(x < 5 and x < 10)</td>
    </tr>
</table>


<ins>Identity operators:</ins>

These are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Description</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>is</td>
        <td>Returns True if both variables are the same object</td>
        <td style="text-align: center">x is y</td>
    </tr>
    <tr>
        <td>is not</td>
        <td>Returns True if both variables are not the same object</td>
        <td style="text-align: center">x is not y</td>
    </tr>
</table>


<ins>Membership operators:</ins>

These are used to test whether a value or variable is found in a sequence.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Description</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>in</td>
        <td>Returns True if a sequence with the specified value is present in the object</td>
        <td style="text-align: center">x in y</td>
    </tr>
    <tr>
        <td>not in</td>
        <td>Returns True if a sequence with the specified value is not present in the object</td>
        <td style="text-align: center">x not in y</td>
    </tr>
</table>

<ins>Bitwise Operators</ins>
These are used to compare binary numbers.

<table style="width: 100%">
    <tr>
        <th>Operator</th>
        <th>Name</th>
        <th>Description</th>
        <th style="text-align: center">Example</th>
    </tr>
    <tr>
        <td>&</td>
        <td>AND</td>
        <td>Sets each bit to 1 if both bits are 1</td>
        <td style="text-align: center">x & y</td>
    </tr>
    <tr>
        <td>|</td>
        <td>OR</td>
        <td>Sets each bit to 1 if one of the two bits is 1</td>
        <td style="text-align: center">x | y</td>
    </tr>
    <tr>
        <td>^</td>
        <td>XOR</td>
        <td>Sets each bit to 1 if only one of two bits is 1</td>
        <td style="text-align: center">x ^ y</td>
    </tr>
    <tr>
        <td>~</td>
        <td>NOT</td>
        <td>Inverts all the bits</td>
        <td style="text-align: center">~x</td>
    </tr>
    <tr>
        <td><<</td>
        <td>Zero fill left shift</td>
        <td>Shift left by pushing zeros in from the right and let the leftmost bits fall off</td>
        <td style="text-align: center">x << y</td>
    </tr>
    <tr>
        <td><<</td>
        <td>Signed right shift</td>
        <td>Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off</td>
        <td style="text-align: center">x >> y</td>
    </tr>
</table>


## 5. Exercises

Create a new file called `lesson_2.py`. We will be using this for all the exercises!

1. Start with a multiline comment at the top of the file. The first line should be "Lesson 2", and the second line should be the current date.
2. Declare a variable `name` and assign your name to it.
3. Declare a variable `age` and assign your age to it.
4. Declare a variable `programmer` and set it to True.
5. Use the `print()` function to print the value of each of the variables.
6. Use the `print()` and `type()` functions to print the type of each of the variables that we have declared up to this point.
7. Declare two variables on one line called `num1` and `num2`, and assign them an integer value.
8. Declare a variable called `total` and assign the sum of `num1` and `num2` to it.


## Sources and Further reading

* [w3schools](https://www.w3schools.com/python/python_operators.asp)
* [Official Python documentation](https://docs.python.org/3/library/operator.html)
* [Real Python](https://realpython.com/python-operators-expressions/)
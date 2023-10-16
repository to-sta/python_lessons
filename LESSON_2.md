#  Lesson  2 - Variables, Data Types and Operators

1. Variables
2. Data Types
3. Operators
4. Exercises

## 1 Variables
Python **variables** are simply containers for storing data values. To create a **variables**, you just assign it a value and then start using it. Assignment is done with a single equals sign **(=)**. A **variable** refers to a memory address (e.g. 0x7ff87bd3e388) in which data is stored.

There are **few rules** regarding variable naming that we have to follow:

* A variable name must start with a letter or the underscore character
* A variable name cannot start with a number
* A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
* Variable names are case-sensitive (name, Name and NAME are three different variables)
* A variable name cannot be any of the Python keywords (e.g. if, else, class, def, int, ...).

The part to the left of the assignment operator is the variable name, and the right side is its value.

```python
variable_name =  4
```
Here are few examples of **valid** and **invalid** variable names:

```python
#Valid variable names:
myvariable = "John"
my_variable = "John"
_myvariable = "John"
myVariable = "John"
MYVARIABLE = "John"
myvariable2 = "John"

#Illegal variable names:
2myvariable = "John"
my-variable = "John"
my var = "John"
```

It is also possible to assign multiple variables in one line:

```python
name, age = "Max", 18
```


Python is a **dynamically typed**, which means that variable types are determined and checked at runtime of the program. We can re-assign variables without worrying about the change of the data type. Re-assigning of a variable will overwrite the value:

```python
variable = 4
print(variable) # 4
variable = "max"
print(variable) # max
```

> [!INFO]
> Variable names should be **lowercase**, with **words separated by underscores** as necessary to improve readability. This is also called **"snake case"**. 
>
>You might be wondering why you would want to start a variable name with a **"_"**, this can be beneficial when there are **reserved key** words like **"class"**. This reserved key word could also make sense in the context of parsing css classes, then we would create a variable _class. 
>
> For more infos about naming conventions regarding functions refer to the [pep8 styleguide](https://peps.python.org/pep-0008/#function-and-variable-names).

## 2 Data Types

**Python** comes with a number of built-in data types. Let's start with the fundmentals, they can be grouped into categories:

* Numeric data types
* String data types
* Boolean data types

<ins>Numeric data types:</ins>
There are two fundamental numeric data types, the `int` data type to represent integer numbers and the `float` data type to represent floating-point numbers.

<ins>String data type:</ins>
A string is a collection of one or more characters put in a single quote, double-quote, or triple-quote. The data type in Python is called **"str"**.

<ins>Boolean data type:</ins>
The boolean value can be of two types only i.e. either `True` or `False`. Numerically, True is equal to **1** and False is equal to **0**. The data type in Python is called **"bool"**.

We can use the built-in function `type()` to determine the data type of a variable or value. For example, calling `type(5)` would return `<class 'int'>`.

```python
print(type(4))                   # int
print(type(3.14))                # float
print(type("Hello World"))       # str
print(type(True))                # bool
```

We can create the datatypes by simply assigning them to a variable or use a **construtor** function. For example if we want to convert a numeric data type to a string we can use the string constructor:

```python
variable = 2
print(type(variable))            # int
variable = str(variable)
print(type(variable))            # str
```

There are constructor functions for all built-in data types (e.g. `bool()`, `int()`, `float()`).

> [!INFO]
> There are more built-in data types than the once mentioned above (e.g **complex numbers** have a numeric data type **complex**). Also datastructures are considered data types, but we will address them later on.


## 3 Operators
Operators are used to perform specifc operations on variables and values. Python comes with a variaty of operators that can be grouped into categories:

* Arithmetic operators
* Assignment operators
* Comparison operators
* Logical operators
* Identity operators
* Membership operators
* Bitwise operators

Let goes through them one by one. 

<ins>Arithmetic operators</ins>

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

Logical operators are used to combine conditional statements and will also return `True` or `False`.

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

## Add Identity, Membership and Bitwise Operators

## 4 Exercises

## Sources and Further reading

* [w3schools](https://www.w3schools.com/python/python_operators.asp)
* [Official Python documentation](https://docs.python.org/3/library/operator.html)
* [Real Python](https://realpython.com/python-operators-expressions/)
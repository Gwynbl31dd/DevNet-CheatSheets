# Python DevNet Cheat sheet

This sheet cheat is trying to focus on the DevNet related need. It does not cover all python

## Python commands

Show list of dependencies

```bash
pip freeze # Raw
pip list # Tabular
```

NOTE: You can add combine pip and freeze to build your requirements.txt ``pip freeze > requirements. txt``

Create a virtual environment

```bash
python -m venv venv
source  venv/bin/activate
# This will save the bin and the lib inside the venv folder
```

Upgrade pip
```bash
python -m pip install --upgrade pip
```

Display Python version

```bash
python -V
```

Get the python path

```bash
wich python
```

Access interactive shell
```bash
python -i
```

## Math Operators

From **Highest** to **Lowest** precedence:

| Operators | Operation         | Example         |
| --------- | ----------------- | --------------- |
| \*\*      | Exponent          | `2 ** 3 = 8`    |
| %         | Modulus/Remainder | `22 % 8 = 6`    |
| //        | Integer division  | `22 // 8 = 2`   |
| /         | Division          | `22 / 8 = 2.75` |
| \*        | Multiplication    | `3 * 3 = 9`     |
| -         | Subtraction       | `5 - 2 = 3`     |
| +         | Addition          | `2 + 2 = 4`     |

Examples of expressions:

```python
>>> 2 + 3 * 6
# 20

>>> (2 + 3) * 6
# 30

>>> 2 ** 8
#256

>>> 23 // 7
# 3

>>> 23 % 7
# 2

>>> (5 - 1) * ((7 + 1) / (3 - 1))
# 16.0
```

## Augmented Assignment Operators

| Operator   | Equivalent      |
| ---------- | --------------- |
| `var += 1` | `var = var + 1` |
| `var -= 1` | `var = var - 1` |
| `var *= 1` | `var = var * 1` |
| `var /= 1` | `var = var / 1` |
| `var %= 1` | `var = var % 1` |

Examples:

```python
>>> greeting = 'Hello'
>>> greeting += ' world!'
>>> greeting
# 'Hello world!'

>>> number = 1
>>> number += 1
>>> number
# 2

>>> my_list = ['item']
>>> my_list *= 3
>>> my_list
# ['item', 'item', 'item']
```

## Data Types

| Data Type              | Examples                                  |
| ---------------------- | ----------------------------------------- |
| Integers               | `-2, -1, 0, 1, 2, 3, 4, 5`                |
| Floating-point numbers | `-1.25, -1.0, --0.5, 0.0, 0.5, 1.0, 1.25` |
| Strings                | `'a', 'aa', 'aaa', 'Hello!', '11 cats'`   |
| Boolean                |  `True,False`                             |

## Concatenation and Replication

String concatenation:

```python
>>> 'Alice' 'Bob'
# 'AliceBob'
```

String Replication:

```python
>>> 'Alice' * 5
# 'AliceAliceAliceAliceAlice'
```

## Variables

You can name a variable anything as long as it obeys the following rules:

1. It can be only one word.

```python
>>> # bad
>>> my variable = 'Hello'

>>> # good
>>> var = 'Hello'
```

2. It can use only letters, numbers, and the underscore (`_`) character.

```python
>>> # bad
>>> %$@variable = 'Hello'

>>> # good
>>> my_var = 'Hello'

>>> # good
>>> my_var_2 = 'Hello'
```

3. It can’t begin with a number.

```python
>>> # this wont work
>>> 23_var = 'hello'
```

4. Variable name starting with an underscore (`_`) are considered as "unuseful".

```python
>>> # _spam should not be used again in the code
>>> _spam = 'Hello'
```

Get the variable type

 ```python
 type(<variable>)
 ```

## Comments

Inline comment:

```python
# This is a comment
```

Multiline comment:

```python
# This is a
# multiline comment
```

Code with a comment:

```python
a = 1  # initialization
```

Please note the two spaces in front of the comment.

Function docstring:

```python
def foo():
    """
    This is a function docstring
    You can also use:
    ''' Function Docstring '''
    """
```

## The print() Function

The `print()` function writes the value of the argument(s) it is given. [...] it handles multiple arguments, floating point-quantities, and strings. Strings are printed without quotes, and a space is inserted between items, so you can format things nicely:

```python
>>> print('Hello world!')
# Hello world!

>>> a = 1
>>> print('Hello world!', a)
# Hello world! 1
```

### The end keyword

The keyword argument `end` can be used to avoid the newline after the output, or end the output with a different string:

```python
phrase = ['printed', 'with', 'a', 'dash', 'in', 'between']
>>> for word in phrase:
...     print(word, end='-')
...
# printed-with-a-dash-in-between-
```

### The sep keyword

The keyword `sep` specify how to separate the objects, if there is more than one:

```python
print('cats', 'dogs', 'mice', sep=',')
# cats,dogs,mice
```

## The input() Function

This function takes the input from the user and converts it into a string:

```python
>>> print('What is your name?')   # ask for their name
>>> my_name = input()
>>> print('Hi, {}'.format(my_name))
# What is your name?
# Martha
# Hi, Martha
```

`input()` can also set a default message without using `print()`:

```python
>>> my_name = input('What is your name? ')  # default message
>>> print('Hi, {}'.format(my_name))
# What is your name? Martha
# Hi, Martha
```

## The len() Function

Evaluates to the integer value of the number of characters in a string, list, dictionary, etc.:

```python
>>> len('hello')
# 5

>>> len(['cat', 3, 'dog'])
# 3
```

<base-warning>
  <base-warning-title>Test of emptiness</base-warning-title>
  <base-warning-content>
    Test of emptiness of strings, lists, dictionaries, etc., should not use
    <code>len</code>, but prefer direct boolean evaluation.
  </base-warning-content>
</base-warning>

Test of emptiness example:

```python
>>> a = [1, 2, 3]

# bad
>>> if len(a) > 0:  # evaluates to True
...     print("the list is not empty!")
...
# the list is not empty!

# good
>>> if a: # evaluates to True
...     print("the list is not empty!")
...
# the list is not empty!
```

## The str(), int(), and float() Functions

These functions allow you to change the type of variable. For example, you can transform from an `integer` or `float` to a `string`:

```python
>>> str(29)
# '29'

>>> str(-3.14)
# '-3.14'
```

Or from a `string` to an `integer` or `float`:

```python
>>> int('11')
# 11

>>> float('3.14')
# 3.14
```

## Format

```python
"duplex {}".format("full")
"interface {name}, port {port}".format(name="gigabitethernet", port="0/1")
"device hostname ipaddress".split(" ")
",".join(['device', 'hostname', 'ipaddress'])
```

New way of formating (Same as .format())

```python
tool = "git clone "
host = "https://github.com/"
org = "CiscoDevNet"
repo = "/netprog_basics"
f"{tool}{host}{org}{repo}"
```

## Input

```python
answer = input("What is the hostname? ")
```

## Comparison Operators

| Operator | Meaning                  |
| -------- | ------------------------ |
| `==`     | Equal to                 |
| `!=`     | Not equal to             |
| `<`      | Less than                |
| `>`      | Greater Than             |
| `<=`     | Less than or Equal to    |
| `>=`     | Greater than or Equal to |

These operators evaluate to True or False depending on the values you give them.

Examples:

```python
>>> 42 == 42
True

>>> 40 == 42
False

>>> 'hello' == 'hello'
True

>>> 'hello' == 'Hello'
False

>>> 'dog' != 'cat'
True

>>> 42 == 42.0
True

>>> 42 == '42'
False
```

## Boolean Operators

There are three Boolean operators: `and`, `or`, and `not`.

The `and` Operator’s _Truth_ Table:

| Expression        | Evaluates to |
| ----------------- | ------------ |
| `True and True`   | `True`       |
| `True and False`  | `False`      |
| `False and True`  | `False`      |
| `False and False` | `False`      |

The `or` Operator’s _Truth_ Table:

| Expression       | Evaluates to |
| ---------------- | ------------ |
| `True or True`   | `True`       |
| `True or False`  | `True`       |
| `False or True`  | `True`       |
| `False or False` | `False`      |

The `not` Operator’s _Truth_ Table:

| Expression  | Evaluates to |
| ----------- | ------------ |
| `not True`  | `False`      |
| `not False` | `True`       |

## Mixing Boolean and Comparison Operators

```python
>>> (4 < 5) and (5 < 6)
True

>>> (4 < 5) and (9 < 6)
False

>>> (1 == 2) or (2 == 2)
True
```

You can also use multiple Boolean operators in an expression, along with the comparison operators:

```python
>>> 2 + 2 == 4 and not 2 + 2 == 5 and 2 * 2 == 2 + 2
True
```

## if Statements

The `if` statement evaluates an expression, and if that expression is `True`, it then executes the following indented code:

```python
>>> name = 'Debora'

>>> if name == 'Debora':
...    print('Hi, Debora')
...
# Hi, Debora

>>> if name != 'George':
...    print('You are not George')
...
# You are not George
```

The `else` statement executes only if the evaluation of the `if` and all the `elif` expressions are `False`:

```python
>>> name = 'Debora'

>>> if name == 'George':
...    print('Hi, George.')
>>> else:
...    print('You are not George')
...
# You are not George
```

Only after the `if` statement expression is `False`, the `elif` statement is evaluated and executed:

```python
>>> name = 'George'

>>> if name == 'Debora':
...    print('Hi Debora!')
>>> elif name == 'George':
...    print('Hi George!')
...
# Hi George!
```

the `elif` and `else` parts are optional.

```python
>>> name = 'Antony'

>>> if name == 'Debora':
...    print('Hi Debora!')
>>> elif name == 'George':
...    print('Hi George!')
>>> else:
...    print('Who are you?')
...
# Who are you?
```

## while Loop Statements

The while statement is used for repeated execution as long as an expression is `True`:

```python
>>> spam = 0
>>> while spam < 5:
...     print('Hello, world.')
...     spam = spam + 1
...
# Hello, world.
# Hello, world.
# Hello, world.
# Hello, world.
# Hello, world.
```

## break Statements

If the execution reaches a `break` statement, it immediately exits the `while` loop’s clause:

```python
>>> while True:
...     name = input('Please type your name: ')
...     if name == 'your name':
...         break
...
>>> print('Thank you!')
# Please type your name: your name
# Thank you!
```

## continue Statements

When the program execution reaches a `continue` statement, the program execution immediately jumps back to the start of the loop.

```python
>>> while True:
...     name = input('Who are you? ')
...     if name != 'Joe':
...         continue
...     password = input('Password? (It is a fish.): ')
...     if password == 'swordfish':
...         break
...
>>> print('Access granted.')
# Who are you? Charles
# Who are you? Debora
# Who are you? Joe
# Password? (It is a fish.): swordfish
# Access granted.
```

## For loop

The `for` loop iterates over a `list`, `tuple`, `dictionary`, `set` or `string`:

```python
>>> pets = ['Bella', 'Milo', 'Loki']
>>> for pet in pets:
...     print(pet)
...
# Bella
# Milo
# Loki
```

## The range() function

The `range()` function returns a sequence of numbers. It starts from 0, increments by 1, and stops before a specified number:

```python
>>> for i in range(5):
...     print(f'Will stop at 5! or 4? ({i})')
...
# Will stop at 5! or 4? (0)
# Will stop at 5! or 4? (1)
# Will stop at 5! or 4? (2)
# Will stop at 5! or 4? (3)
# Will stop at 5! or 4? (4)
```

The `range()` function can also modify it's 3 defaults arguments. The first two will be the `start` and `stop` values, and the third will be the `step` argument. The step is the amount that the variable is increased by after each iteration.

```python
# range(start, stop, step)
>>> for i in range(0, 10, 2):
...    print(i)
...
# 0
# 2
# 4
# 6
# 8
```

You can even use a negative number for the step argument to make the for loop count down instead of up.

```python
>>> for i in range(5, -1, -1):
...     print(i)
...
# 5
# 4
# 3
# 2
# 1
# 0
```

Functions:

```python
def function_name(arg_1, arg_2):
    statements...
    return value
```

* Cannot start with a number [0-9]
* Cannot conflict with a language keyword
* Can contain: [A-Za-z0-9_-]

## Built in data type


| Name  type()       | Example                                                                | Notes       |
| -----------        | ------------                                                           | ------------ |
| `list`             | `["ssh", "tcp", "ftp", 19.2, 20.1]`                                    | Ordered list of items,Mutable (can be changed after created),Items can be different data types, Can contain duplicate items |
| `tuple`            | `("FillmoreDC", "NorthWestRegion")`                                    | Just like a list; except: Immutable (cannot be changed) |
| `dictionary  dict` | `{"ipv4address": "192.168.0.1", "traffic": "inbound", "port": 40044}`  | Unordered key-value pairs,Keys don’t have to be same data type,Values don’t have to be same data type ,Keys are unique; must be immutable |



### List 

```python
lookup = ["ssh", "tcp", "ftp", 19.2, 20.1]

lookup.append("sftp")

tuple (immutable list):

territory = ("FillmoreDC", "NorthWestRegion")
territory[0]
```

### Dictionary

```python
devicehost = {"ipv4address": "192.168.0.10", "traffic": "inbound", "port": 40044}
devicehost["traffic"]
```

## Other python collections

| Collection         | Description                                                             |
| -----------        | ------------                                                           |
| `Counter`             | `Dict subclass for counting hashable objects`                                    |
| `OrderedDict`            | `Dict subclass that remembers the order entries were added`                                    |
| `defaultdict` | `Dict subclass that calls a factory function to supply missing values`  |
| `UserDict` | `Wrapper around dictionary objects for easier dict subclassing`  |
| `UserList` | `Wrapper around list objects for easier list subclassing`  |
| `UserString` | `Wrapper around string objects for easier string subclassing`  |

### OrderedDict

Maintain the order of the item added to them

```python
from collections import OrderedDict
metrics = OrderedDict()
metrics["finance"] = 95
metrics["health"] = 25
metrics["comms"] = 55
```

1. We did have to import OrderedDict before we could use it.
2. We added the key-value pairs to it incrementally, to demonstrate how it maintains the order in which they were added.
3. When you look at the contents of the OrderedDict, it looks a little different: OrderedDict(<list of tuples>).

 ## Structure
  
 ```python
  #!/usr/bin/env python
"""Demonstrate module vs. locally scoped variables."""

# Create a module variable
module_variable = "I am a module variable."

# Define a function that expects to receive a value for an argument variable
def my_function(argument_variable):
    """Showing how module, argument, and local variables are used."""
    # Create a local variable
    local_variable = "I am a local variable."

    print(module_variable, "...and I can be accessed inside a function.")
    print(argument_variable, "...and I can be passed to a function.")
    print(local_variable, "...and I can ONLY be accessed inside a function.")

# Call the function; supplying the value for the argument variable
my_function(argument_variable="I am a argument variable.")

# Let's try accessing that local variable here at module scope
print("\nTrying to access local_variable outside of its function...")
try:
    print(local_variable)
except NameError as error:
    print(error)
```
  

  
## OOP

Retrieve object methods

```python
dir(object)
```
  
### Methods
  
```python
class Parrot:
    
    # instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # instance method
    def sing(self, song):
        return "{} sings {}".format(self.name, song)

    def dance(self):
        return "{} is now dancing".format(self.name)

# instantiate the object
blu = Parrot("Blu", 10)

# call our instance methods
print(blu.sing("'Happy'"))
print(blu.dance())
```
  
### Inheritance
  
```python
# parent class
class Bird:
    
    def __init__(self):
        print("Bird is ready")

    def whoisThis(self):
        print("Bird")

    def swim(self):
        print("Swim faster")

# child class
class Penguin(Bird):

    def __init__(self):
        # call super() function
        super().__init__()
        print("Penguin is ready")

    def whoisThis(self):
        print("Penguin")

    def run(self):
        print("Run faster")

peggy = Penguin()
peggy.whoisThis()
peggy.swim()
peggy.run()
```

### Encapsulation

```python
class Computer:

    def __init__(self):
        self.__maxprice = 900

    def sell(self):
        print("Selling Price: {}".format(self.__maxprice))

    def setMaxPrice(self, price):
        self.__maxprice = price

c = Computer()
c.sell()

# change the price
c.__maxprice = 1000
c.sell()

# using setter function
c.setMaxPrice(1000)
c.sell()
```
  
### Polymorphism 
  
```python
class Parrot:

    def fly(self):
        print("Parrot can fly")
    
    def swim(self):
        print("Parrot can't swim")

class Penguin:

    def fly(self):
        print("Penguin can't fly")
    
    def swim(self):
        print("Penguin can swim")

# common interface
def flying_test(bird):
    bird.fly()

#instantiate objects
blu = Parrot()
peggy = Penguin()

# passing the object
flying_test(blu)
flying_test(peggy)
```
## Files

```python
file = open("intro-python/parsing-json/pep20.txt", mode="r")
file_contents = file.read()
print(file_contents)
file.close()
```

```python
with open("intro-python/parsing-json/pep20.txt", mode="r") as file:
     file_firstline = file.readline()
     print(file_firstline)
```

## JSON
  
### Parse
  
```python
import json
import os
from pprint import pprint
# Get the absolute path for the directory where this file is located "here"
here = os.path.abspath(os.path.dirname("interface-config.json"))
# Read in the JSON text
with open(os.path.join(here, "interface-config.json")) as file:
    json_text = file.read()
# Display the type of the json_text variable
print("json_text is a", type(json_text))

# Display the contents of the json_text variable
print(json_text)

# Use the json module to parse the JSON string into native Python data
json_data = json.loads(json_text)

# Display the type of the json_data variable
print("json_data is a", type(json_data))

# Display the contents of the json_data variable
pprint(json_data)  
```
  
### Nested data
  
```python
json_data["ietf-interfaces:interface"]["ietf-ip:ipv4"]["address"][0]["ip"]
```
  
```python
rules_list = ["allow", "deny", "delete"]
for rule in rules_list:
    print(rule)
```
  
 ## HTTP Requests
 
```python
import requests
x = requests.get('https://w3schools.com/python/demopage.htm')
print(x.text)
```
  

| Method         | Description                                                             |
| -----------        | ------------                                                           |
| `delete(url, args)`             | `Sends a DELETE request to the specified url`                                    |
| `get(url, params, args)`            | `Sends a GET request to the specified url`                                    |
| `head(url, args)` | `Sends a HEAD request to the specified url`  |
| `patch(url, data, args)` | `Sends a PATCH request to the specified url`  |
| `post(url, data, json, args)` | `Sends a POST request to the specified url`  |
| `put(url, data, args)` | `Sends a PUT request to the specified url`  |
| `request(method, url, args)` | `Sends a request of the specified method to the specified url`  |
  

  
  

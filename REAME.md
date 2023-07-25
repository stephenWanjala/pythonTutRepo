1. Introduction to Python
## 
Python is a high-level, interpreted programming language known for its simplicity and readability. It is versatile and can be used for various purposes, such as web development, data analysis, artificial intelligence, and automation.

### Hello, World!

Let's start with the traditional "Hello, World!" program to get familiar with Python syntax:

```python
print("Hello, World!")
```

Output:

    Hello, World!

2. Variables and Data Types
In Python, you don't need to declare variables explicitly; they are created automatically when you assign a value.

Variables and Basic Data Types
``` python
# Integer
age = 25

# Float
height = 5.9

# String
name = "John Doe"

# Boolean
is_student = True

# NoneType
    my_variable = None
```

## Dynamic Typing
Python is dynamically typed, which means you can change the type of a variable on the fly.

```python
x = 10
print(x)  # Output: 10

x = "Hello"
print(x)  # Output: Hello
```

3. Basic Input and Output
Input

```python
name = input("Enter your name: ")
print("Hello, " + name)
```

### Output Formatting

```python
age = 30
print("I am {} years old.".format(age))
```

4. Control Flow
    If-Else Statements

### python Loops
For Loop

```python

for i in range(5):
    print(i)
```

While Loop


```python

count = 0

while count < 5:
    print(count)
    count += 1
```

5. Lists, Tuples, and Dictionaries
Lists

```python
fruits = ["apple", "banana", "orange"]
print(fruits[0])       # Output: apple
print(len(fruits))     # Output: 3
```

Tuples

```python

point = (10, 20)
print(point[0])        # Output: 10
Dictionaries
```

```python

person = {
    "name": "John",
    "age": 25,
    "is_student": True
}

print(person["name"])  # Output: John
```

6. Functions
Creating Functions

```python

def add_numbers(a, b):
    return a + b

result = add_numbers(5, 3)
print(result)          # Output: 8
```

Lambda Functions
```python

square = lambda x: x ** 2
print(square(5))       # Output: 25
```

7. Object-Oriented Programming (OOP)
Classes and Objects

```python

class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return "Woof!"

dog1 = Dog("Buddy", 3)
print(dog1.name)       # Output: Buddy
print(dog1.bark())     # Output: Woof!
```

8. File Handling
Reading from a File

```python

with open("myfile.txt", "r") as file:
    contents = file.read()
    print(contents)
```

Writing to a File

```python

with open("myfile.txt", "w") as file:
    file.write("Hello, World!")
```

9. Modules and Packages
Creating a Module
Create a Python file named mymodule.py.

```python

def greet(name):
    return f"Hello, {name}!"
```

Using a Module

```python

import mymodule

message = mymodule.greet("Alice")
print(message)        # Output: Hello, Alice!

```

10. Exception Handling

```python

try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print(result)
except ZeroDivisionError:
    print("Cannot divide by zero.")
except ValueError:
    print("Invalid input. Please enter a valid number.")

```

## Decorators

Decorators are functions that modify the behavior of other functions or methods. They allow you to extend the functionality of existing functions without changing their code. Decorators are commonly used for tasks like logging, authorization, caching, etc.

Example: Simple Decorator
```python

def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("Something is happening before the function is called.")
        result = func(*args, **kwargs)
        print("Something is happening after the function is called.")
        return result
    return wrapper

@my_decorator
def say_hello(name):
    return f"Hello, {name}!"

message = say_hello("Alice")
print(message)
```


    Output:

    Something is happening before the function is called.
    Something is happening after the function is called.
    Hello, Alice!
Generators
Generators are a way to create iterators in Python. Unlike lists that store all their values in memory, generators produce values on-the-fly, which makes them memory-efficient for dealing with large datasets.

Example: Fibonacci Generator

```python

def fibonacci_generator(n):
    a, b = 0, 1
    count = 0
    while count < n:
        yield a
        a, b = b, a + b
        count += 1

fibonacci_sequence = fibonacci_generator(10)
for num in fibonacci_sequence:
    print(num, end=" ")
```

    Output:

    
    0 1 1 2 3 5 8 13 21 34
## Context Managers

Context managers provide a convenient way to manage resources like files, database connections, network connections, etc. They ensure that resources are properly initialized and cleaned up, even if an exception occurs.

Example: Using with Statement for File Handling
```python

with open("example.txt", "r") as file:
    contents = file.read()
    print(contents)
# File will be automatically closed outside the 'with' block
```

Example: Creating a Custom Context Manager

```python

class MyContextManager:
    def __enter__(self):
        print("Entering the context")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Exiting the context")
        if exc_type is not None:
            print(f"Exception occurred: {exc_type}, {exc_value}")
        return False


with MyContextManager() as context:
    print("Inside the context")
    # Simulate an exception
    # raise ValueError("Something went wrong")
```

 Output:

    Entering the context
    Inside the context
    Exiting the context
    Exception occurred: <class 'ValueError'>, Something went wrong
Context managers are useful for handling resources properly, closing files, releasing locks, and more.

## Strings

Strings are sequences of characters and are widely used in Python for text processing and manipulation.

### String Indexing and Slicing

```python

my_string = "Hello, World!"

print(my_string[0])       # Output: H
print(my_string[7:])      # Output: World!
print(my_string[:5])      # Output: Hello
print(my_string[::2])     # Output: Hlo ol!
```

### String Methods

Python provides various built-in methods for string manipulation:

```python

my_string = "Hello, World!"

print(my_string.upper())           # Output: HELLO, WORLD!
print(my_string.lower())           # Output: hello, world!
print(my_string.replace("Hello", "Hi"))  # Output: Hi, World!
print(my_string.split(", "))       # Output: ['Hello', 'World!']
print(my_string.startswith("Hello")) # Output: True
print(my_string.endswith("World!"))  # Output: True
```

### String Formatting

```python

name = "Alice"
age = 30

# Using f-strings (Python 3.6+)
formatted_string = f"My name is {name} and I am {age} years old."
print(formatted_string)
# Output: My name is Alice and I am 30 years old.

# Using format() method
formatted_string = "My name is {} and I am {} years old.".format(name, age)
print(formatted_string)
# Output: My name is Alice and I am 30 years old.
```

### Functions

Functions are blocks of code that perform specific tasks and can be reused throughout the program.

Defining Functions

```python
def greet(name):
    return f"Hello, {name}!"

def add_numbers(a, b):
    return a + b

def is_even(number):
    return number % 2 == 0
```

Calling Functions

```python
message = greet("Alice")
print(message)                 # Output: Hello, Alice!

result = add_numbers(5, 3)
print(result)                  # Output: 8

print(is_even(10))             # Output: True
print(is_even(7))              # Output: False
```

Default Arguments

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))          # Output: Hello, Alice!
print(greet("Bob", "Hi"))      # Output: Hi, Bob!
```

Variable-Length Arguments

```python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total

print(sum_numbers(1, 2, 3))        # Output: 6
print(sum_numbers(10, 20, 30, 40)) # Output: 100
```

Anonymous Functions (Lambda Functions)

```python
square = lambda x: x ** 2
print(square(5))                 # Output: 25

add = lambda a, b: a + b
print(add(3, 5))                 # Output: 8
```

## Higher order functions

1. Map
The map() function applies a given function to all items in an iterable (e.g., a list) and returns a new iterable containing the results.

```python
def square(x):
    return x ** 2

numbers = [1, 2, 3, 4, 5]
squared_numbers = map(square, numbers)
print(list(squared_numbers))  # Output: [1, 4, 9, 16, 25]
```

2. Filter
The filter() function filters elements from an iterable based on a given function that returns a Boolean value (True or False).

```python
def is_even(x):
    return x % 2 == 0

numbers = [1, 2, 3, 4, 5]
even_numbers = filter(is_even, numbers)
print(list(even_numbers))     # Output: [2, 4]
```

3. Reduce
The reduce() function (originally from the functools module in Python 2, but moved to functools module in Python 3) reduces an iterable to a single value by successively applying a binary function to the elements from left to right.

```python
from functools import reduce

def add(x, y):
    return x + y

numbers = [1, 2, 3, 4, 5]
sum_of_numbers = reduce(add, numbers)
print(sum_of_numbers)         # Output: 15
```

4. Sorted
The sorted() function sorts elements of an iterable based on a specified key or a given function.

```python
names = ["Alice", "Bob", "Charlie", "David"]
sorted_names = sorted(names, key=len)
print(sorted_names)           # Output: ['Bob', 'Alice', 'David', 'Charlie']
```

5. Function as a Return Value
Higher-order functions can also return functions as results.

```python
def multiplier(factor):
    def multiply(number):
        return number * factor
    return multiply

multiply_by_2 = multiplier(2)
print(multiply_by_2(5))       # Output: 10
```

### Lists

Lists are ordered collections of items, and they can contain elements of different data types.

## List Comprehensions

List comprehensions provide a concise way to create lists based on existing lists or other iterables.

```python
# Example 1: Create a list of squares of numbers from 1 to 5
squares = [x ** 2 for x in range(1, 6)]
print(squares)  # Output: [1, 4, 9, 16, 25]

# Example 2: Filter even numbers from a list
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
even_numbers = [x for x in numbers if x % 2 == 0]
print(even_numbers)  # Output: [2, 4, 6, 8]
```

### List Methods

Python provides several built-in methods for list manipulation:

```python
fruits = ["apple", "banana", "orange"]

fruits.append("pear")           # Add an element at the end
fruits.insert(1, "grape")       # Insert an element at index 1
fruits.remove("banana")         # Remove the first occurrence of "banana"
fruits.pop(0)                   # Remove and return the element at index 0
fruits.sort()                   # Sort the list in ascending order
fruits.reverse()                # Reverse the list

print(fruits)                   # Output: ['orange', 'pear', 'grape']
```

### Tuples

Tuples are similar to lists but are immutable, meaning their elements cannot be changed after creation.

```python
# Creating a tuple
point = (10, 20)

# Accessing elements
x, y = point
print(x, y)     # Output: 10 20

# Tuples can be used as keys in dictionaries
coordinates = {(1, 2): "A", (3, 4): "B"}
print(coordinates[(1, 2)])     # Output: A
```

### Dictionaries

Dictionaries are unordered collections of key-value pairs.

```python
# Creating a dictionary
person = {
    "name": "John",
    "age": 25,
    "is_student": True
}

# Accessing values
print(person["name"])           # Output: John

# Adding or updating values
person["occupation"] = "Engineer"
person["age"] = 26

# Checking if a key exists
if "name" in person:
    print("Name exists in the dictionary.")
```

Dictionary Methods

```python
# Getting all keys and values
keys = person.keys()
values = person.values()

# Removing a key-value pair
removed_value = person.pop("is_student")

# Clearing the dictionary
person.clear()

# Merging two dictionaries (Python 3.9+)
person2 = {"name": "Alice", "age": 30}
person |= person2

print(person)  # Output: {'name': 'Alice', 'age': 30, 'occupation': 'Engineer'}
```

1. Lists
Lists are ordered collections of items, and they can contain elements of different data types.
List Comprehensions provide a concise way to create lists based on existing lists or other iterables.

```python
# Example 1: Create a list of squares of numbers from 1 to 5
squares = [x ** 2 for x in range(1, 6)]

# Example 2: Filter even numbers from a list
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
even_numbers = [x for x in numbers if x % 2 == 0]
```

Common List Methods:

```python
fruits = ["apple", "banana", "orange"]

fruits.append("pear")           # Add an element at the end
fruits.insert(1, "grape")       # Insert an element at index 1
fruits.remove("banana")         # Remove the first occurrence of "banana"
fruits.pop(0)                   # Remove and return the element at index 0
fruits.sort()                   # Sort the list in ascending order
fruits.reverse()                # Reverse the list
```

2. Tuples
Tuples are similar to lists but are immutable, meaning their elements cannot be changed after creation.

```python
# Creating a tuple
point = (10, 20)

# Accessing elements
x, y = point
```

3. Dictionaries
Dictionaries are unordered collections of key-value pairs.

```python
# Creating a dictionary
person = {
    "name": "John",
    "age": 25,
    "is_student": True
}

# Accessing values
print(person["name"])

# Adding or updating values
person["occupation"] = "Engineer"
person["age"] = 26

# Checking if a key exists
if "name" in person:
    print("Name exists in the dictionary.")
```

Common Dictionary Methods:

```python
# Getting all keys and values
keys = person.keys()
values = person.values()

# Removing a key-value pair
removed_value = person.pop("is_student")

# Clearing the dictionary
person.clear()

# Merging two dictionaries (Python 3.9+)
person2 = {"name": "Alice", "age": 30}
person |= person2
```

Understanding Python data structures and their methods is crucial for efficient data manipulation and organization. Lists, tuples, and dictionaries offer various functionalities that cater to different use cases. With these concepts at your disposal, you can write more powerful and organized Python programs.




```python
new_list = [expression for item in iterable if condition]
```

expression: The operation or transformation applied to each item in the iterable.
item: The variable representing each element in the iterable.
iterable: The original list or other iterable.
condition (optional): A filter that determines whether the item should be included in the new list.
Examples:
Creating a list of squares of numbers from 1 to 5:

```python
squares = [x ** 2 for x in range(1, 6)]
# Output: [1, 4, 9, 16, 25]
```

Filtering even numbers from a list:

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
even_numbers = [x for x in numbers if x % 2 == 0]
# Output: [2, 4, 6, 8]
```

Using conditions with list comprehensions:

```python
# Create a list of odd squares from 1 to 10
odd_squares = [x ** 2 for x in range(1, 11) if x % 2 != 0]
# Output: [1, 9, 25, 49, 81]
Working with strings:
python
Copy code
# Create a list of uppercase characters from a string
message = "Hello, World!"
uppercase_chars = [char.upper() for char in message if char.isalpha()]
# Output: ['H', 'E', 'L', 'L', 'O', 'W', 'O', 'R', 'L', 'D']
```

### Python List Comprehensions - Advanced Concepts

List comprehensions in Python are a versatile and powerful feature that allows concise and expressive ways to create lists. Let's explore some advanced concepts to harness the full potential of list comprehensions.

1. Nested List Comprehensions
List comprehensions can be nested, allowing you to create more complex lists or even lists of lists.

Example: Creating a 2D matrix using nested list comprehensions

```python
matrix = [[i * j for j in range(1, 4)] for i in range(1, 4)]
# Output: [[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

2. Using Conditional Expressions (Ternary Operator)
List comprehensions can include conditional expressions to specify different outcomes based on the item value.

Example: Create a list containing "Even" or "Odd" based on the number's parity.

```python
numbers = [1, 2, 3, 4, 5, 6]
even_odd_labels = ["Even" if num % 2 == 0 else "Odd" for num in numbers]
# Output: ['Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even']
```

3. Multiple Iterables in List Comprehensions (Zip Function)
You can use the zip() function with list comprehensions to iterate over multiple lists simultaneously.

Example: Create a list of tuples containing elements from two lists.

```python
names = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]
student_data = [(name, score) for name, score in zip(names, scores)]
# Output: [('Alice', 85), ('Bob', 92), ('Charlie', 78)]
```

4. Filtering with Multiple Conditions
List comprehensions can include multiple conditions to filter elements based on more complex criteria.

Example: Create a list of numbers greater than 5 and even.

```python
numbers = [1, 6, 3, 8, 4, 9]
result = [num for num in numbers if num > 5 and num % 2 == 0]
# Output: [6, 8]
```

5. Set and Dictionary Comprehensions
Similar to list comprehensions, Python also supports set and dictionary comprehensions.

Set Comprehensions:

```python

numbers = [1, 2, 3, 4, 4, 5, 5, 6]
unique_numbers = {num for num in numbers}
# Output: {1, 2, 3, 4, 5, 6}
```

Dictionary Comprehensions:

```python

names = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]
student_data = {name: score for name, score in zip(names, scores)}
# Output: {'Alice': 85, 'Bob': 92, 'Charlie': 78}
```

6. Using Functions with List Comprehensions
You can apply functions to the elements in the list comprehension.

Example: Create a list of squares of numbers using a function.

```python
def square(x):
    return x ** 2

numbers = [1, 2, 3, 4, 5]
squares = [square(x) for x in numbers]
# Output: [1, 4, 9, 16, 25]
```

List comprehensions are a powerful and expressive feature in Python that allows you to create lists efficiently and elegantly.
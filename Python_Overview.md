# Python Overview

## Empty Main Function

Python does not require a main function like C. The code starts executing from the top of the script.

```python
# No explicit main function in Python
# Code starts executing from the top
# No need for return statements
```

## Simple Variable Declaration

```python
# Variable declaration and initialization
age = 25
height = 1.75
name = "John"

# Print the variables
print(f"Age: {age}, Height: {height}, Name: {name}")
```

## Control Structure - Conditional If
Only one branch will run.
```python
# Conditional if, elif, else
number = 10

if number > 0:
    print("Number is positive")
elif number < 0:
    print("Number is negative")
else:
    print("Number is zero")
```

## Control Structure - For Loop

```python
# For loop
for i in range(5):
    print(f"Iteration: {i}")
```

## Control Structure - While Loop

```python
# While loop
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1
```

## Simple Function

```python
# Function to add two numbers
def add_numbers(a, b):
    return a + b

result = add_numbers(4, 5)
print(f"Result: {result}")
```

## Empty Class

A class is a structure to generate complex data types, for that, it needs a `constructor` method.

```python
class Person:
    pass
```

## Class with Attributes

The constructor `__init__()` is used to 'make' some variables inside the objects, only the variables with `self` are saved.

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def calculate_area(self):
        return self.width * self.height

# Instantiation
rect = Rectangle(3.0, 4.0)
area = rect.calculate_area()
print(f"Area of rectangle: {area}")
```

## Lists (Equivalent to Arrays)
### List Declaration and Initialization

```python
# List declaration and initialization
numbers = [1, 2, 3, 4, 5]

# Accessing and printing elements of the list
for i in range(len(numbers)):
    print(f"Element {i}: {numbers[i]}")
```

Bonus: In Python, There's no need to manage memory allocation and deallocation like in languages such as C, there is a `garbage collector` for that.
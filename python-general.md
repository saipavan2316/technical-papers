# Python General Cheatsheet

## 1. Print Statement
Used to display output.

```python
print("Hello World")
print(10)
```

## 2. Variables
Used to store data.

```python
name = "Pavan"
age = 23
salary = 25000
```

## 3. Data Types

```python
name = "Python"       # str
age = 23              # int
price = 99.5          # float
is_active = True      # bool
numbers = [1, 2, 3]   # list
```

Check data type:

```python
print(type(name))
```

## 4. Taking User Input

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
```

## 5. Type Conversion

```python
x = "100"
y = int(x)

a = 10
b = str(a)
```

Common conversions:
- `int()`
- `float()`
- `str()`
- `list()`
- `tuple()`

## 6. Operators

| Operator | Meaning |
|---|---|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |
| `//` | Floor division |
| `%` | Modulus |
| `**` | Power |
| `==` | Equal |
| `!=` | Not equal |
| `>` | Greater than |
| `<` | Less than |

## 7. Conditional Statements

```python
age = 20

if age >= 18:
    print("Adult")
elif age > 12:
    print("Teenager")
else:
    print("Child")
```

## 8. Loops

For loop:

```python
for i in range(5):
    print(i)
```

While loop:

```python
i = 0

while i < 5:
    print(i)
    i += 1
```

## 9. Functions

```python
def greet(name):
    return "Hello " + name

print(greet("Pavan"))
```

## 10. List Comprehension

```python
numbers = [1, 2, 3, 4, 5]

squares = [x * x for x in numbers]

print(squares)
```

## 11. Exception Handling

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input")
finally:
    print("Program completed")
```

## 12. Importing Modules

```python
import math

print(math.sqrt(25))
```

Import a specific function:

```python
from math import factorial

print(factorial(5))
```

## 13. Useful Built-in Functions

| Function | Purpose |
|---|---|
| `len()` | Returns length |
| `type()` | Returns data type |
| `sum()` | Returns sum |
| `max()` | Returns maximum |
| `min()` | Returns minimum |
| `sorted()` | Returns sorted data |
| `range()` | Generates a sequence |
| `enumerate()` | Returns index and value |
| `zip()` | Combines iterables |
| `round()` | Rounds a number |

## 14. Comments

```python
# This is a single-line comment
```

## 15. String Formatting

```python
name = "Pavan"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

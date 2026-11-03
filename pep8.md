# Python PEP 8 Cheatsheet

## 1. What is PEP 8?

PEP 8 is the official Python style guide. It provides coding conventions to make Python code readable and consistent.

## 2. Indentation

Use 4 spaces for each indentation level.

```python
if age >= 18:
    print("Adult")
```

## 3. Variable Naming

Use `snake_case` for variables.

```python
user_name = "Pavan"
total_price = 500
```

Avoid:

```python
userName = "Pavan"
totalPrice = 500
```

## 4. Function Naming

Use `snake_case` for function names.

```python
def calculate_total():
    pass
```

## 5. Class Naming

Use `PascalCase` for class names.

```python
class StudentDetails:
    pass
```

## 6. Constants

Use uppercase letters with underscores.

```python
MAX_LIMIT = 100
PI_VALUE = 3.14
```

## 7. Spaces Around Operators

Use spaces around operators.

Correct:

```python
total = price + tax
```

Avoid:

```python
total=price+tax
```

## 8. Line Length

Keep lines reasonably short. PEP 8 recommends a maximum of 79 characters for code lines.

## 9. Blank Lines

Use blank lines to separate functions and classes.

```python
def greet():
    print("Hello")


def welcome():
    print("Welcome")
```

## 10. Imports

Place imports at the beginning of the file.

```python
import os
import math

import requests
```

## 11. Comments

Write clear and meaningful comments.

```python
# Calculate the total price
total = price + tax
```

## 12. String Quotes

Use single or double quotes consistently.

```python
name = "Pavan"
city = 'Warangal'
```

## 13. Boolean Comparisons

Use direct boolean checks.

Correct:

```python
if is_active:
    print("Active")
```

Avoid:

```python
if is_active == True:
    print("Active")
```

## 14. Useful Tools

- `flake8` - Checks code style.
- `black` - Automatically formats Python code.
- `pylint` - Checks code quality.

Install:

```bash
pip install flake8 black pylint
```

Run:

```bash
flake8 main.py
black main.py
pylint main.py
```

## 15. Remember

- Use meaningful variable names.
- Follow consistent indentation.
- Keep functions small and readable.
- Avoid unnecessary code.
- Follow consistent formatting.

# Python Arrays Cheatsheet

## 1. Lists

Python commonly uses lists to store collections of values.

```python
numbers = [10, 20, 30, 40, 50]
```

## 2. Accessing Elements

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[0])   # 10
print(numbers[-1])  # 50
```

## 3. Slicing

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])  # [20, 30, 40]
print(numbers[:3])   # [10, 20, 30]
print(numbers[2:])   # [30, 40, 50]
```

## 4. Adding Elements

```python
numbers.append(60)          # Add one element
numbers.insert(1, 15)       # Insert at index
numbers.extend([70, 80])    # Add multiple elements
```

## 5. Removing Elements

```python
numbers.remove(20)  # Remove value
numbers.pop()       # Remove last element
numbers.pop(0)      # Remove element at index
numbers.clear()     # Remove all elements
```

## 6. Updating Elements

```python
numbers = [10, 20, 30]

numbers[1] = 25

print(numbers)
```

## 7. Common List Methods

| Method | Purpose |
|---|---|
| `append()` | Add an element |
| `extend()` | Add multiple elements |
| `insert()` | Insert at index |
| `remove()` | Remove a value |
| `pop()` | Remove and return an element |
| `sort()` | Sort the list |
| `reverse()` | Reverse the list |
| `index()` | Find element index |
| `count()` | Count occurrences |
| `copy()` | Create a shallow copy |
| `clear()` | Remove all elements |

## 8. Sorting

```python
numbers = [5, 2, 8, 1, 3]

numbers.sort()                  # Ascending
numbers.sort(reverse=True)      # Descending

print(sorted(numbers))          # Returns a new sorted list
```

## 9. Looping Through Lists

```python
numbers = [10, 20, 30]

for num in numbers:
    print(num)
```

Using enumerate:

```python
for index, value in enumerate(numbers):
    print(index, value)
```

## 10. List Comprehension

```python
numbers = [1, 2, 3, 4, 5]

squares = [x ** 2 for x in numbers]

print(squares)
```

## 11. Checking Elements

```python
numbers = [10, 20, 30]

print(20 in numbers)      # True
print(50 not in numbers)  # True
```

## 12. Nested Lists

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0][1])  # 2
```

## 13. Tuples

Tuples are ordered and immutable.

```python
numbers = (10, 20, 30)

print(numbers[0])
print(len(numbers))
```

## 14. Sets

Sets store unique elements.

```python
numbers = {1, 2, 2, 3, 4}

numbers.add(5)
numbers.remove(2)

print(numbers)
```

## 15. Python Array Module

Python also provides an `array` module for storing elements of the same basic type.

```python
from array import array

numbers = array('i', [10, 20, 30, 40])

numbers.append(50)

print(numbers)
```

Common type codes:
- `i` - Signed integer
- `f` - Float
- `d` - Double precision float

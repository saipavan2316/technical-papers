# Python Dictionary Cheatsheet

## 1. What is a Dictionary?

A dictionary stores data in key-value pairs.

```python
student = {
    "name": "Pavan",
    "age": 23,
    "city": "Warangal"
}
```

## 2. Accessing Values

```python
print(student["name"])
print(student["age"])
```

Using `get()`:

```python
print(student.get("name"))
print(student.get("marks", 0))
```

`get()` returns a default value if the key does not exist.

## 3. Adding Elements

```python
student["course"] = "Python"
```

## 4. Updating Elements

```python
student["age"] = 24
```

## 5. Removing Elements

```python
student.pop("age")       # Remove specific key
student.popitem()        # Remove last inserted item
del student["city"]      # Delete specific key
student.clear()          # Remove all items
```

## 6. Dictionary Methods

| Method | Purpose |
|---|---|
| `keys()` | Returns all keys |
| `values()` | Returns all values |
| `items()` | Returns key-value pairs |
| `get()` | Gets value by key |
| `update()` | Updates dictionary |
| `pop()` | Removes specified key |
| `popitem()` | Removes last item |
| `clear()` | Removes all items |
| `copy()` | Creates a shallow copy |
| `setdefault()` | Gets value or inserts default |

## 7. Looping Through Dictionary

Loop through keys:

```python
for key in student:
    print(key)
```

Loop through values:

```python
for value in student.values():
    print(value)
```

Loop through keys and values:

```python
for key, value in student.items():
    print(key, value)
```

## 8. Checking Keys

```python
print("name" in student)
print("salary" not in student)
```

## 9. Dictionary Length

```python
print(len(student))
```

## 10. Nested Dictionaries

```python
students = {
    "student1": {
        "name": "Pavan",
        "age": 23
    },
    "student2": {
        "name": "Rahul",
        "age": 22
    }
}

print(students["student1"]["name"])
```

## 11. Dictionary Comprehension

```python
numbers = [1, 2, 3, 4]

squares = {x: x ** 2 for x in numbers}

print(squares)
```

Output:

```python
{1: 1, 2: 4, 3: 9, 4: 16}
```

## 12. Merging Dictionaries

```python
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}

dict1.update(dict2)

print(dict1)
```

## 13. Counting Elements Using Dictionary

```python
numbers = [1, 2, 2, 3, 3, 3]

count = {}

for num in numbers:
    count[num] = count.get(num, 0) + 1

print(count)
```

Output:

```python
{1: 1, 2: 2, 3: 3}
```

## 14. Important Points

- Dictionaries store key-value pairs.
- Keys must be unique.
- Dictionaries are mutable.
- Values can be of any data type.
- Keys must be hashable (commonly strings, numbers, and tuples of hashable values).
- Dictionaries preserve insertion order in modern Python.

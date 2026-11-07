# Python Strings Cheat Sheet

Strings are immutable sequences of Unicode characters.

## 1. String Creation

```python
s1 = "Python"
s2 = 'Programming'
s3 = """Multiline
string"""

name = "Sai"
age = 23
message = f"My name is {name}, age {age}"
```

## 2. Indexing and Slicing

```python
s = "Programming"

s[0]      # 'P'
s[-1]     # 'g'
s[0:4]    # 'Prog'
s[::2]    # Every second character
s[::-1]   # Reverse string
s[2:]     # From index 2
s[:5]     # Up to index 5 (exclusive)
```

Syntax: `string[start:stop:step]`

## 3. Important String Methods

| Method | Purpose |
|---|---|
| `lower()` | Convert to lowercase |
| `upper()` | Convert to uppercase |
| `title()` | Capitalize each word |
| `capitalize()` | Capitalize first character |
| `strip()` | Remove leading/trailing whitespace |
| `lstrip()` | Remove leading whitespace |
| `rstrip()` | Remove trailing whitespace |
| `replace(a, b)` | Replace substring |
| `split(sep)` | Split into a list |
| `join(iterable)` | Join elements into a string |
| `find(sub)` | Return first index or -1 |
| `index(sub)` | Return first index or raise ValueError |
| `count(sub)` | Count occurrences |
| `startswith()` | Check starting substring |
| `endswith()` | Check ending substring |

Example:
```python
text = "  hello python  "

text.strip()
text.upper()
text.replace("python", "world")
text.split()
```

## 4. split() vs join()

```python
sentence = "Python is powerful"

words = sentence.split()
# ['Python', 'is', 'powerful']

result = "-".join(words)
# Python-is-powerful
```

`split()` converts a string into a list.

`join()` combines an iterable of strings into one string.

## 5. String Formatting

### f-strings
```python
name = "Sai"
salary = 40000

print(f"{name} earns {salary}")
print(f"Salary: {salary:.2f}")
print(f"Salary: {salary:,}")
```

### format()
```python
print("Hello, {}".format("Sai"))
print("{name} is {age}".format(name="Sai", age=23))
```

## 6. String Immutability

Strings cannot be modified in place.

```python
s = "hello"

# s[0] = "H"  # TypeError

s = "H" + s[1:]
print(s)  # Hello
```

Methods like `replace()` return new strings rather than modifying the original.

## 7. Character Checking Methods

| Method | Checks |
|---|---|
| `isalpha()` | Only alphabetic characters |
| `isdigit()` | Only digit characters |
| `isalnum()` | Letters or digits |
| `isspace()` | Only whitespace |
| `islower()` | All cased characters lowercase |
| `isupper()` | All cased characters uppercase |
| `istitle()` | Title case |

```python
"Python".isalpha()   # True
"123".isdigit()      # True
"Python123".isalnum() # True
"Hello World".istitle() # True
```

## 8. Useful String Operations

```python
s = "python"

len(s)             # 6
"py" in s          # True
"java" not in s    # True
s * 3              # pythonpythonpython
s + " language"    # Concatenation
```

## 9. Common Interview Patterns

### Reverse a string
```python
s = "python"
reversed_s = s[::-1]
```

### Check palindrome
```python
def is_palindrome(s):
    return s == s[::-1]
```

### Character frequency
```python
from collections import Counter

s = "programming"
frequency = Counter(s)
```

### Remove duplicate characters (preserve order)
```python
s = "programming"
result = "".join(dict.fromkeys(s))
```

### Count words
```python
sentence = "Python is easy to learn"
word_count = len(sentence.split())
```

### Check anagram
```python
from collections import Counter

def is_anagram(a, b):
    return Counter(a) == Counter(b)
```

## 10. Important Notes

- Strings are immutable.
- Strings support indexing, slicing and iteration.
- `find()` returns `-1` when the substring is absent.
- `index()` raises `ValueError` when absent.
- `join()` is generally preferred over repeated string concatenation when building strings in a loop.
- Python strings use Unicode, so they support characters from different languages.

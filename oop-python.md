# Python OOP Cheat Sheet

## 1. Classes and Objects
A class is a blueprint; an object is an instance of a class.

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def display(self):
        print(self.name, self.salary)

emp = Employee("Sai", 40000)
emp.display()
```

- `self`: Reference to the current instance.
- `__init__`: Constructor, called when an object is created.
- Instance variables: Belong to individual objects.
- Class variables: Shared across instances.

## 2. Instance vs Class Variables

```python
class Employee:
    company = "Google"  # Class variable

    def __init__(self, name):
        self.name = name  # Instance variable
```

Access:
```python
emp = Employee("Sai")
print(emp.name)
print(Employee.company)
```

## 3. Instance, Class and Static Methods

```python
class Employee:
    company = "Google"

    def __init__(self, name):
        self.name = name

    def display(self):             # Instance method
        return self.name

    @classmethod
    def change_company(cls, name):
        cls.company = name

    @staticmethod
    def is_valid_salary(salary):
        return salary > 0
```

| Method | First parameter | Use |
|---|---|---|
| Instance | `self` | Access instance data |
| Class | `cls` | Access/modify class data |
| Static | None | Utility operations |

## 4. Inheritance

Allows a class to reuse and extend another class.

```python
class Animal:
    def speak(self):
        print("Animal makes a sound")

class Dog(Animal):
    def speak(self):
        print("Bark")

dog = Dog()
dog.speak()
```

- Single inheritance
- Multiple inheritance
- Multilevel inheritance
- Hierarchical inheritance
- Hybrid inheritance

### super()

Calls methods from the parent class.

```python
class Dog(Animal):
    def __init__(self, name):
        super().__init__()
        self.name = name
```

## 5. Encapsulation

Combines data and methods while controlling access to internal attributes.

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def get_balance(self):
        return self.__balance
```

Naming conventions:
- `name`: Public
- `_name`: Protected by convention
- `__name`: Name mangling (not truly private)

## 6. Polymorphism

Different objects can provide different implementations of the same method.

```python
class Dog:
    def sound(self):
        return "Bark"

class Cat:
    def sound(self):
        return "Meow"

for animal in [Dog(), Cat()]:
    print(animal.sound())
```

Python also supports operator overloading through special methods.

```python
class Point:
    def __init__(self, x):
        self.x = x

    def __add__(self, other):
        return Point(self.x + other.x)
```

## 7. Abstraction

Hides implementation details and exposes essential functionality.

```python
from abc import ABC, abstractmethod

class Payment(ABC):
    @abstractmethod
    def pay(self, amount):
        pass

class UpiPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount} using UPI")
```

An abstract class cannot be instantiated while it has unimplemented abstract methods.

## 8. Important Dunder Methods

| Method | Purpose |
|---|---|
| `__init__` | Initialize object |
| `__str__` | Human-readable representation |
| `__repr__` | Developer representation |
| `__len__` | Implements `len()` |
| `__eq__` | Implements `==` |
| `__add__` | Implements `+` |
| `__lt__` | Implements `<` |

## 9. Composition

One class contains an instance of another class. It represents a HAS-A relationship.

```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()
```

**Quick Revision**
- IS-A → Inheritance
- HAS-A → Composition
- Same interface, different behavior → Polymorphism
- Hide implementation details → Abstraction
- Control access to data → Encapsulation

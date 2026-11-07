# SOLID Principles in Python

SOLID represents five principles used to design maintainable, extensible and loosely coupled software.

## 1. S — Single Responsibility Principle (SRP)

A class should have only one responsibility or one reason to change.

**Bad design:**
```python
class User:
    def save_to_database(self):
        pass

    def send_email(self):
        pass
```

**Better design:**
```python
class User:
    def __init__(self, name):
        self.name = name

class UserRepository:
    def save(self, user):
        pass

class EmailService:
    def send(self, user):
        pass
```

Each class handles a separate responsibility.

## 2. O — Open/Closed Principle (OCP)

Software entities should be open for extension but closed for modification.

**Bad design:**
```python
class Discount:
    def calculate(self, customer_type, price):
        if customer_type == "regular":
            return price * 0.1
        elif customer_type == "premium":
            return price * 0.2
```

Adding new customer types requires modifying existing logic.

**Better design:**
```python
from abc import ABC, abstractmethod

class Discount(ABC):
    @abstractmethod
    def calculate(self, price):
        pass

class RegularDiscount(Discount):
    def calculate(self, price):
        return price * 0.1

class PremiumDiscount(Discount):
    def calculate(self, price):
        return price * 0.2
```

New discount types can be added without changing existing implementations.

## 3. L — Liskov Substitution Principle (LSP)

A child class should be usable wherever its parent class is expected without breaking the program's behavior.

**Bad design:**
```python
class Bird:
    def fly(self):
        print("Flying")

class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins cannot fly")
```

Penguin violates the expected behavior of Bird.

**Better design:**
```python
class Bird:
    pass

class FlyingBird(Bird):
    def fly(self):
        print("Flying")

class Sparrow(FlyingBird):
    pass

class Penguin(Bird):
    pass
```

Do not force subclasses to implement behavior they cannot support.

## 4. I — Interface Segregation Principle (ISP)

Clients should not be forced to depend on methods they do not use.

**Bad design:**
```python
class Worker:
    def work(self):
        pass

    def eat(self):
        pass
```

A robot worker should not need an eat method.

**Better design:**
```python
class Workable:
    def work(self):
        pass

class Eatable:
    def eat(self):
        pass

class Human(Workable, Eatable):
    pass

class Robot(Workable):
    pass
```

Keep interfaces small and focused.

## 5. D — Dependency Inversion Principle (DIP)

High-level modules should depend on abstractions rather than concrete implementations.

**Bad design:**
```python
class MySQLDatabase:
    def connect(self):
        print("Connected to MySQL")

class UserService:
    def __init__(self):
        self.database = MySQLDatabase()
```

UserService is tightly coupled to MySQLDatabase.

**Better design:**
```python
from abc import ABC, abstractmethod

class Database(ABC):
    @abstractmethod
    def connect(self):
        pass

class MySQLDatabase(Database):
    def connect(self):
        print("Connected to MySQL")

class PostgreSQLDatabase(Database):
    def connect(self):
        print("Connected to PostgreSQL")

class UserService:
    def __init__(self, database: Database):
        self.database = database

    def execute(self):
        self.database.connect()

service = UserService(PostgreSQLDatabase())
service.execute()
```

The dependency is injected instead of created inside UserService.

## Quick Revision

| Principle | Main idea |
|---|---|
| SRP | One responsibility per class |
| OCP | Extend without modifying existing code |
| LSP | Subclasses must be substitutable |
| ISP | Prefer small, focused interfaces |
| DIP | Depend on abstractions, not concrete classes |

**Remember:** SOLID is not about creating more classes. It is about reducing coupling and making changes safer.

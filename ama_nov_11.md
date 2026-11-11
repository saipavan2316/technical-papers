# AMA Questions - NOV 11 2026

## Question 1 - Why do we need SQL?
### Answer -
SQL (Structured Query Language) is used to create, manage, retrieve, and manipulate data stored in relational databases.

## Question 2 - Difference between find() and rfind()
### Answer -
- find() - Returns the index of the first occurrence of a substring.
- rfind() - Returns the index of the last occurrence of a substring.

## Question 3 - Difference between class method and instance method
### Answer -
- Instance Method - Uses `self` to access and modify instance attributes.
- Class Method - Uses `cls` to access and modify class attributes. It is declared using `@classmethod`.

## Question 4 - What are DDL commands?
### Answer -
DDL (Data Definition Language) commands are used to define and modify database structures.
- CREATE - Creates database objects.
- ALTER - Modifies existing database structures.
- DROP - Deletes database objects.
- TRUNCATE - Removes all rows from a table.

## Question 5 - Use of garbage collection
### Answer -
Garbage collection automatically identifies and removes unused objects from memory to free up memory.

## Question 6 - Difference between dict and defaultdict
### Answer -
- dict - Accessing a non-existing key raises a KeyError.
- defaultdict - Automatically creates a default value for a non-existing key.

## Question 7 - What are *args and **kwargs in Python?
### Answer -
- *args - Used to pass multiple positional arguments to a function as a tuple.
- **kwargs - Used to pass multiple keyword arguments to a function as a dictionary.

## Question 8 - When do we use "__" while declaring an instance variable?
### Answer -
Using double underscores before an instance variable triggers name mangling, which helps prevent direct access to the variable from outside the class.

## Question 9 - What are class variables?
### Answer -
Class variables are variables declared inside a class but outside its methods. They are shared among all instances of the class.

## Question 10 - Command for pattern matching in SQL
### Answer -
- LIKE - Used to match patterns in strings.
- ILIKE - Used for case-insensitive pattern matching in PostgreSQL.
- % - Matches zero or more characters.
- _ - Matches exactly one character.

## Question 11 - Difference between sort() and sorted()
### Answer -
- sort() - Sorts the original list in place and returns None.
- sorted() - Returns a new sorted list without modifying the original iterable.

## Question 12 - Difference between mutable and immutable
### Answer -
- Mutable - Objects whose values can be changed after creation. Example: List, Dictionary, Set.
- Immutable - Objects whose values cannot be changed after creation. Example: String, Tuple, Integer.

## Question 13 - What is a primary key?
### Answer -
A primary key is a column or combination of columns that uniquely identifies each row in a table. It cannot contain NULL or duplicate values.

## Question 14 - Use of unique key in SQL
### Answer -
A UNIQUE constraint ensures that all values in a column or combination of columns are unique. It prevents duplicate values.

## Question 15 - Difference between kill and kill -9
### Answer -
- kill - Sends a termination signal (SIGTERM by default), allowing a process to shut down gracefully.
- kill -9 - Sends SIGKILL, which immediately terminates a process without allowing cleanup.

## Question 16 - What is encapsulation?
### Answer -
Encapsulation is the process of wrapping data and methods into a single unit (class) and restricting direct access to internal data.

## Question 17 - What is a foreign key?
### Answer -
A foreign key is a column or combination of columns that references a primary key or unique key in another table. It maintains relationships and referential integrity between tables.

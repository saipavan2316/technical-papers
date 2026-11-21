# AMA - Questions 21-Nov

## 1. What is the difference between Flexbox and Grid

### Answer:

- Flexbox: A one-dimensional layout system used to arrange elements in a row or column.
- Grid: A two-dimensional layout system used to arrange elements in rows and columns.

## 2. What is the difference between remove() and discard() in Python

### Answer:

Both methods are used to remove elements from a set.

- remove(): Removes the specified element. Raises a `KeyError` if the element does not exist.
- discard(): Removes the specified element. Does not raise an error if the element does not exist.

## 3. What is the difference between div and span

### Answer:

- `<div>`: A block-level element used to group larger sections of HTML content.
- `<span>`: An inline element used to group small portions of content within a line.

## 4. How can we highlight text in HTML

### Answer:

We can use the `<mark>` tag to highlight text.

Example: `<mark>Hello World</mark>`

## 5. What is the difference between Python and Python3

### Answer:

- Python: Refers to the Python programming language in general and may refer to older versions.
- Python 3: The modern version of Python with updated syntax, features, and improvements over Python 2.

Python 2 is discontinued, and Python 3 is currently used.

## 6. What is an anchor query in HTML

### Answer:

An anchor link is used to navigate to a specific section within the same webpage or another webpage.

We use the `<a>` tag with the `href` attribute.

Example:

```html
<a href="#about">Go to About</a>

<h2 id="about">About Section</h2>
```

Here, clicking the link takes us to the element with `id="about"`.

## 7. What is CSS

### Answer:

CSS stands for Cascading Style Sheets. It is used to control the appearance and layout of HTML elements, including colors, fonts, spacing, and positioning.

## 8. When we insert values into a table where a column has a default value and we explicitly insert NULL, which value will be stored

### Answer:

`NULL` will be stored instead of the default value.

The default value is applied when the column is omitted from the INSERT statement or when the `DEFAULT` keyword is used.

Example:

```sql
CREATE TABLE students (
    id INT,
    name VARCHAR(50) DEFAULT 'Unknown'
);

INSERT INTO students (id) VALUES (1);
-- name = 'Unknown'

INSERT INTO students (id, name) VALUES (2, NULL);
-- name = NULL
```

## 9. What is HTML

### Answer:

HTML stands for HyperText Markup Language. It is the standard markup language used to define the structure and content of webpages.

## 10. List some HTML tags

### Answer:

- `<html>` – Root element.
- `<head>` – Contains metadata.
- `<title>` – Defines the webpage title.
- `<body>` – Contains visible content.
- `<h1>` to `<h6>` – Headings.
- `<p>` – Paragraph.
- `<a>` – Creates hyperlinks.
- `<img>` – Displays images.
- `<div>` – Block-level container.
- `<span>` – Inline container.
- `<ul>` – Unordered list.
- `<ol>` – Ordered list.
- `<li>` – List item.
- `<table>` – Creates a table.
- `<form>` – Creates a form.

## 11. What is the use of an index in SQL

### Answer:

An index is a database object used to speed up data retrieval operations.

It helps the database find records faster without scanning the entire table.

Example:

```sql
CREATE INDEX idx_student_name
ON students(name);
```

**Note:** Indexes improve read performance but require additional storage and can slow down INSERT, UPDATE, and DELETE operations.

## 12. What are the types of CSS

### Answer:

There are three ways to apply CSS:

1. Inline CSS – Written directly inside an HTML element using the `style` attribute.
2. Internal CSS – Written inside the `<style>` tag in the HTML document.
3. External CSS – Written in a separate `.css` file and linked to HTML.

## 13. How can we pass multiple conditions in SQL

### Answer:

We can use logical operators to combine multiple conditions.

- AND – All conditions must be true.
- OR – At least one condition must be true.
- NOT – Negates a condition.

Example:

```sql
SELECT *
FROM students
WHERE age > 20 AND marks > 80;
```

```sql
SELECT *
FROM students
WHERE age > 20 OR marks > 80;
```

## 14. What is the difference between kill -9 and kill -15 in Linux

### Answer:

Both commands are used to terminate processes, but they send different signals.

- `kill -15 PID` – Sends SIGTERM. Requests the process to terminate gracefully, allowing it to perform cleanup.
- `kill -9 PID` – Sends SIGKILL. Immediately terminates the process without allowing cleanup.

SIGTERM is generally preferred before using SIGKILL.

## 15. What is the full form of HTML and CSS

### Answer:

- HTML – HyperText Markup Language.
- CSS – Cascading Style Sheets.

## 16. What is justify-content in CSS

### Answer:

`justify-content` is a CSS property used to align and distribute items along the main axis of a Flexbox or Grid container.

Common values:

- `flex-start` – Aligns items at the beginning.
- `flex-end` – Aligns items at the end.
- `center` – Aligns items at the center.
- `space-between` – Distributes items with equal space between them.
- `space-around` – Adds space around each item.
- `space-evenly` – Distributes equal space between and around items.

Example:

```css
.container {
    display: flex;
    justify-content: center;
}
```

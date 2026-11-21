# HTML Cheatsheet

## 1. HTML Boilerplate

Basic structure of every HTML document.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Webpage</title>
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

- `<!DOCTYPE html>` – Declares the document as HTML5.
- `<html>` – Root element.
- `<head>` – Contains metadata and document information.
- `<title>` – Sets the browser tab title.
- `<body>` – Contains visible webpage content.

## 2. HTML Headings and Paragraphs

```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Third Level Heading</h3>
<h4>Fourth Level Heading</h4>
<h5>Fifth Level Heading</h5>
<h6>Sixth Level Heading</h6>

<p>This is a paragraph.</p>
<br>
<hr>
```

- `<h1>` to `<h6>` – Headings, from highest to lowest level.
- `<p>` – Paragraph.
- `<br>` – Line break.
- `<hr>` – Thematic break between sections.

## 3. Text Formatting Elements

```html
<b>Bold text</b>
<strong>Important text</strong>

<i>Italic text</i>
<em>Emphasized text</em>

<u>Underlined text</u>
<mark>Highlighted text</mark>

<small>Small text</small>
<del>Deleted text</del>
<ins>Inserted text</ins>

<sub>Subscript</sub>
<sup>Superscript</sup>
```

**Important differences:**
- `<b>` – Visual bold formatting.
- `<strong>` – Indicates strong importance.
- `<i>` – Alternate voice or mood.
- `<em>` – Indicates emphasis.

## 4. Links (Anchor Element)

Used to navigate between webpages or resources.

```html
<a href="https://www.google.com">Visit Google</a>

<a href="about.html">About Us</a>

<a href="https://www.google.com" target="_blank">
    Open in New Tab
</a>

<a href="mailto:test@example.com">Send Email</a>

<a href="tel:+911234567890">Call Us</a>
```

Common attributes:
- `href` – Specifies the destination.
- `target="_blank"` – Opens the link in a new tab.
- `title` – Provides additional information.

## 5. Images

```html
<img src="image.jpg" alt="Description of image">

<img src="image.jpg" alt="Nature" width="300" height="200">
```

Attributes:
- `src` – Image location.
- `alt` – Alternative text if the image cannot load; also helps accessibility.
- `width` – Image width.
- `height` – Image height.

## 6. Lists

### Ordered List

Displays items with numbers.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

### Unordered List

Displays items with bullets.

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ul>
```

### Description List

Used for terms and their descriptions.

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

## 7. HTML Tables

Used to display data in rows and columns.

```html
<table>
    <caption>Student Details</caption>

    <thead>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Age</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>1</td>
            <td>Pavan</td>
            <td>23</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Rahul</td>
            <td>22</td>
        </tr>
    </tbody>
</table>
```

Important elements:
- `<table>` – Creates a table.
- `<tr>` – Table row.
- `<th>` – Header cell.
- `<td>` – Data cell.
- `<thead>` – Groups header rows.
- `<tbody>` – Groups body rows.
- `<tfoot>` – Groups footer rows.
- `<caption>` – Table title.

Useful attributes:
- `colspan` – Makes a cell span multiple columns.
- `rowspan` – Makes a cell span multiple rows.

Example:

```html
<td colspan="2">Combined Columns</td>
<td rowspan="2">Combined Rows</td>
```

## 8. HTML Forms

Forms collect information from users.

```html
<form action="/submit" method="POST">

    <label for="username">Username:</label>
    <input type="text" id="username" name="username">

    <br><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email">

    <br><br>

    <label for="password">Password:</label>
    <input type="password" id="password" name="password">

    <br><br>

    <button type="submit">Submit</button>

</form>
```

### Common Input Types

```html
<input type="text">
<input type="password">
<input type="email">
<input type="number">
<input type="tel">
<input type="date">
<input type="time">
<input type="file">
<input type="color">
<input type="range">
<input type="checkbox">
<input type="radio">
<input type="submit">
<input type="reset">
```

### Other Form Elements

```html
<textarea name="message" rows="4" cols="30"></textarea>

<select name="country">
    <option value="india">India</option>
    <option value="usa">USA</option>
</select>

<button type="button">Click Me</button>
```

### Important Form Attributes

- `action` – URL where form data is submitted.
- `method` – HTTP method (`GET` or `POST`).
- `name` – Identifies the submitted form field.
- `value` – Default or submitted value.
- `placeholder` – Displays a hint.
- `required` – Makes a field mandatory.
- `readonly` – Prevents editing but allows submission.
- `disabled` – Disables the field and excludes it from form submission.
- `min` / `max` – Minimum and maximum values.
- `maxlength` – Maximum number of characters.

## 9. HTML Semantic Elements

Semantic elements clearly describe the purpose of their content.

```html
<header>
    <h1>Website Name</h1>
</header>

<nav>
    <a href="home.html">Home</a>
    <a href="about.html">About</a>
</nav>

<main>
    <section>
        <h2>About Us</h2>
        <p>About our website.</p>
    </section>

    <article>
        <h2>Latest Article</h2>
        <p>Article content.</p>
    </article>

    <aside>
        Related information
    </aside>
</main>

<footer>
    Copyright 2026
</footer>
```

Common semantic elements:

- `<header>` – Introductory content or header.
- `<nav>` – Navigation links.
- `<main>` – Main content of the document.
- `<section>` – Thematic grouping of content.
- `<article>` – Independent, self-contained content.
- `<aside>` – Related or supplementary content.
- `<footer>` – Footer information.

## 10. Block-Level and Inline Elements

### Block-Level Elements

- Start on a new line.
- Generally occupy the available width.

Examples:

```html
<div>Block element</div>
<p>Paragraph</p>
<h1>Heading</h1>
<section>Section</section>
```

### Inline Elements

- Do not normally start on a new line.
- Occupy only the space they need.

Examples:

```html
<span>Inline element</span>
<a href="#">Link</a>
<strong>Important</strong>
<em>Emphasized</em>
```

## 11. HTML Div and Span

### Div

A generic block-level container.

```html
<div>
    <h2>Welcome</h2>
    <p>This is inside a div.</p>
</div>
```

### Span

A generic inline container.

```html
<p>
    My favourite language is
    <span>Python</span>.
</p>
```

- `<div>` – Groups larger sections of content.
- `<span>` – Groups small portions of inline content.

## 12. HTML Audio and Video

### Audio

```html
<audio controls>
    <source src="music.mp3" type="audio/mpeg">
    Your browser does not support audio.
</audio>
```

### Video

```html
<video controls width="400">
    <source src="video.mp4" type="video/mp4">
    Your browser does not support video.
</video>
```

Common attributes:
- `controls` – Displays playback controls.
- `autoplay` – Automatically starts playback.
- `loop` – Repeats playback.
- `muted` – Starts with audio muted.
- `poster` – Specifies a video preview image.

## 13. HTML Iframe

Embeds another webpage or external resource.

```html
<iframe
    src="https://example.com"
    width="500"
    height="300"
    title="Example Website">
</iframe>
```

Common attributes:
- `src` – URL of the embedded resource.
- `width` – Width of the iframe.
- `height` – Height of the iframe.
- `title` – Accessible description.

## 14. HTML Global Attributes

Global attributes can be used on most HTML elements.

| Attribute | Purpose |
|---|---|
| `id` | Unique identifier for an element |
| `class` | Groups elements under a common name |
| `title` | Additional information |
| `style` | Inline styling |
| `hidden` | Hides an element |
| `lang` | Specifies the language |
| `dir` | Specifies text direction |
| `contenteditable` | Makes content editable |
| `tabindex` | Controls keyboard focus order |

Example:

```html
<p id="intro" class="description" title="Introduction">
    Welcome to HTML.
</p>
```

## 15. HTML Entities

Entities represent reserved characters and special symbols.

| Entity | Output |
|---|---|
| `&lt;` | < |
| `&gt;` | > |
| `&amp;` | & |
| `&quot;` | " |
| `&apos;` | ' |
| `&nbsp;` | Non-breaking space |
| `&copy;` | © |
| `&reg;` | ® |

Example:

```html
<p>5 &lt; 10</p>
<p>Copyright &copy; 2026</p>
```

## 16. HTML Comments

Comments are not displayed in the browser.

```html
<!-- This is an HTML comment -->

<!--
This is a
multiline comment.
-->
```

## 17. Important HTML Concepts

### Void Elements

Elements that do not have closing tags or child content.

Examples:

```html
<br>
<hr>
<img src="image.jpg" alt="Image">
<input type="text">
<meta charset="UTF-8">
<link rel="icon" href="favicon.ico">
```

### Nesting

Placing one element inside another.

```html
<div>
    <h2>Heading</h2>
    <p>This is a paragraph.</p>
</div>
```

Always close elements in the correct order.

### Attributes

Attributes provide additional information about HTML elements.

```html
<a href="https://example.com" target="_blank">
    Visit Website
</a>
```

Here:
- `href` and `target` are attributes.
- Their values are `"https://example.com"` and `"_blank"`.

### HTML5

HTML5 is the modern standard of HTML. It introduced semantic elements, native audio and video support, and several new form input types.

---

## Quick Revision

| Concept | HTML Element |
|---|---|
| Heading | `<h1>` to `<h6>` |
| Paragraph | `<p>` |
| Link | `<a>` |
| Image | `<img>` |
| Ordered list | `<ol>` |
| Unordered list | `<ul>` |
| List item | `<li>` |
| Table | `<table>` |
| Form | `<form>` |
| Input | `<input>` |
| Button | `<button>` |
| Container | `<div>` |
| Inline container | `<span>` |
| Navigation | `<nav>` |
| Main content | `<main>` |
| Section | `<section>` |
| Article | `<article>` |
| Header | `<header>` |
| Footer | `<footer>` |
| Audio | `<audio>` |
| Video | `<video>` |
| Embedded page | `<iframe>` |

**Remember:** HTML defines the structure and meaning of webpage content. CSS handles presentation, and JavaScript handles behaviour. Those will be covered separately.

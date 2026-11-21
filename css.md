# CSS Cheatsheet

## 1. What is CSS?

CSS (Cascading Style Sheets) is used to style and design HTML elements.

There are three ways to apply CSS.

### Inline CSS

CSS directly inside an HTML element.

```html
<p style="color: red;">Hello World</p>
```

### Internal CSS

CSS inside the `<style>` element.

```html
<head>
    <style>
        p {
            color: blue;
        }
    </style>
</head>
```

### External CSS

CSS in a separate `.css` file.

**index.html**
```html
<link rel="stylesheet" href="style.css">
```

**style.css**
```css
p {
    color: green;
}
```

External CSS is generally preferred because it separates structure from presentation.

---

## 2. CSS Syntax

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
    font-size: 32px;
}
```

- Selector – Selects the HTML element.
- Property – Specifies what to change.
- Value – Specifies how it should look.
- Declaration – A property and its value.

## 3. CSS Selectors

Selectors are used to target HTML elements.

### Element Selector

Selects all elements of a particular type.

```css
p {
    color: red;
}
```

### Class Selector

Selects elements with a particular class.

```css
.heading {
    color: blue;
}
```

HTML:
```html
<h1 class="heading">Hello</h1>
```

### ID Selector

Selects an element with a particular ID.

```css
#title {
    color: green;
}
```

HTML:
```html
<h1 id="title">Welcome</h1>
```

### Universal Selector

Selects all elements.

```css
* {
    margin: 0;
    padding: 0;
}
```

### Grouping Selector

Applies the same styles to multiple selectors.

```css
h1, h2, p {
    font-family: Arial;
}
```

### Descendant Selector

Selects elements inside another element at any nesting level.

```css
div p {
    color: red;
}
```

### Child Selector

Selects only direct children.

```css
div > p {
    color: blue;
}
```

### Attribute Selector

Selects elements based on their attributes.

```css
input[type="text"] {
    border: 1px solid black;
}
```

---

## 4. CSS Colors and Backgrounds

### Colors

```css
h1 {
    color: red;
}

p {
    color: #ff0000;
}

div {
    color: rgb(255, 0, 0);
}
```

Common color formats:

- Color names: `red`, `blue`, `green`
- HEX: `#ffffff`
- RGB: `rgb(255, 255, 255)`
- RGBA: `rgba(255, 0, 0, 0.5)`
- HSL: `hsl(0, 100%, 50%)`

### Background Properties

```css
body {
    background-color: lightblue;
}

div {
    background-image: url("image.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}
```

Important properties:

- `background-color`
- `background-image`
- `background-repeat`
- `background-position`
- `background-size`
- `background-attachment`

---

## 5. CSS Text and Fonts

### Text Properties

```css
p {
    color: black;
    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;
    text-indent: 20px;
    line-height: 1.5;
    letter-spacing: 2px;
    word-spacing: 5px;
}
```

### Font Properties

```css
h1 {
    font-family: Arial, sans-serif;
    font-size: 32px;
    font-weight: bold;
    font-style: italic;
}
```

Common properties:

| Property | Purpose |
|---|---|
| `font-family` | Font type |
| `font-size` | Font size |
| `font-weight` | Font thickness |
| `font-style` | Normal or italic |
| `text-align` | Text alignment |
| `text-decoration` | Underline, overline, etc. |
| `text-transform` | Uppercase or lowercase |
| `line-height` | Space between lines |

---

## 6. CSS Units

CSS uses different units to define sizes and distances.

### Absolute Units

| Unit | Meaning |
|---|---|
| `px` | Pixels |
| `cm` | Centimeters |
| `mm` | Millimeters |
| `in` | Inches |
| `pt` | Points |

### Relative Units

| Unit | Meaning |
|---|---|
| `%` | Relative to the relevant parent or reference size |
| `em` | Relative to the element's font size (for font-size, relative to parent) |
| `rem` | Relative to the root element's font size |
| `vw` | 1% of viewport width |
| `vh` | 1% of viewport height |
| `vmin` | 1% of the smaller viewport dimension |
| `vmax` | 1% of the larger viewport dimension |

Example:

```css
.container {
    width: 80%;
    height: 50vh;
    font-size: 1rem;
    padding: 2em;
}
```

---

## 7. CSS Box Model

Every HTML element is treated as a rectangular box.

The box model consists of:

1. Content – Actual text or image.
2. Padding – Space between content and border.
3. Border – Surrounds padding and content.
4. Margin – Space outside the border.

```css
div {
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
```

### Box Sizing

```css
* {
    box-sizing: border-box;
}
```

- `content-box` – Width and height apply only to content.
- `border-box` – Width and height include content, padding, and border.

`border-box` is commonly used to make sizing easier.

---

## 8. Margin and Padding

### Margin

Creates space outside an element.

```css
div {
    margin: 20px;
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 20px;
    margin-left: 25px;
}
```

### Padding

Creates space inside an element.

```css
div {
    padding: 20px;
    padding-top: 10px;
    padding-left: 15px;
}
```

### Shorthand

```css
div {
    margin: 10px 20px 30px 40px;
}
```

Order: Top → Right → Bottom → Left.

```css
div {
    margin: 10px 20px;
}
```

Order: Top/Bottom → Left/Right.

---

## 9. CSS Borders and Outlines

### Borders

```css
div {
    border: 2px solid black;
    border-radius: 10px;
}
```

Individual properties:

```css
div {
    border-width: 2px;
    border-style: solid;
    border-color: red;
    border-radius: 5px;
}
```

Border styles include:

- `solid`
- `dashed`
- `dotted`
- `double`
- `none`

### Outline

```css
input {
    outline: 2px solid blue;
}
```

**Difference:**
- Border is part of the box model.
- Outline is drawn outside the border and does not occupy layout space.

---

## 10. CSS Display Property

Controls how elements are displayed in the document.

### Block

- Starts on a new line.
- Takes available width by default.
- Supports width and height.

```css
div {
    display: block;
}
```

### Inline

- Does not start on a new line.
- Takes only the required width.
- Width and height generally do not apply.

```css
span {
    display: inline;
}
```

### Inline-Block

- Stays inline.
- Supports width and height.

```css
span {
    display: inline-block;
    width: 100px;
    height: 50px;
}
```

### None

Completely removes the element from the layout.

```css
.hidden {
    display: none;
}
```

---

## 11. CSS Position Property

Controls how elements are positioned.

### Static

Default positioning.

```css
div {
    position: static;
}
```

### Relative

Positioned relative to its normal position.

```css
div {
    position: relative;
    top: 10px;
    left: 20px;
}
```

### Absolute

Positioned relative to its nearest positioned ancestor.

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 10px;
    right: 10px;
}
```

### Fixed

Positioned relative to the viewport and stays in place when scrolling.

```css
div {
    position: fixed;
    bottom: 10px;
    right: 10px;
}
```

### Sticky

Behaves like relative positioning until a specified scroll position is reached.

```css
header {
    position: sticky;
    top: 0;
}
```

### Z-Index

Controls the stacking order of overlapping elements.

```css
div {
    position: absolute;
    z-index: 10;
}
```

---

## 12. CSS Flexbox

Flexbox is a one-dimensional layout system used to arrange elements in rows or columns.

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

### Important Flexbox Properties

| Property | Purpose |
|---|---|
| `display: flex` | Enables Flexbox |
| `flex-direction` | Row or column |
| `justify-content` | Alignment along main axis |
| `align-items` | Alignment along cross axis |
| `flex-wrap` | Allows items to wrap |
| `gap` | Space between items |
| `align-content` | Aligns multiple flex lines |
| `flex-grow` | Controls how items grow |
| `flex-shrink` | Controls how items shrink |
| `flex-basis` | Initial main size of an item |

### Justify Content Values

```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

### Align Items Values

```css
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: stretch;
align-items: baseline;
```

---

## 13. CSS Grid

Grid is a two-dimensional layout system used to arrange elements in rows and columns.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### Important Grid Properties

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px;
    grid-template-rows: 100px 100px;
    column-gap: 20px;
    row-gap: 10px;
}
```

Other useful properties:

- `grid-template-columns` – Defines columns.
- `grid-template-rows` – Defines rows.
- `grid-column` – Controls column placement and spanning.
- `grid-row` – Controls row placement and spanning.
- `gap` – Space between rows and columns.
- `grid-template-areas` – Defines named layout areas.

Example:

```css
.item {
    grid-column: span 2;
}
```

### Fractional Unit

`fr` represents a fraction of the available space.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
}
```

---

## 14. CSS Overflow

Controls what happens when content exceeds an element's dimensions.

```css
div {
    width: 200px;
    height: 100px;
    overflow: auto;
}
```

Values:

- `visible` – Content overflows visibly (default).
- `hidden` – Hides overflowing content.
- `scroll` – Adds scrolling.
- `auto` – Adds scrolling when needed.
- `clip` – Clips overflowing content without scrolling.

---

## 15. CSS Pseudo-Classes

Pseudo-classes define special states of elements.

```css
a:hover {
    color: red;
}

button:active {
    background-color: blue;
}

input:focus {
    border: 2px solid green;
}

li:first-child {
    color: red;
}

li:last-child {
    color: blue;
}

li:nth-child(2) {
    color: green;
}
```

Common pseudo-classes:

| Pseudo-class | Purpose |
|---|---|
| `:hover` | Mouse over an element |
| `:active` | Element being activated |
| `:focus` | Element has focus |
| `:first-child` | First child |
| `:last-child` | Last child |
| `:nth-child(n)` | Selects a child by position |
| `:checked` | Checked input |
| `:disabled` | Disabled element |
| `:not()` | Excludes matching elements |

---

## 16. CSS Pseudo-Elements

Pseudo-elements style specific parts of an element.

```css
p::first-letter {
    font-size: 30px;
}

p::first-line {
    color: red;
}

h1::before {
    content: "★ ";
}

h1::after {
    content: " ★";
}

::selection {
    background-color: yellow;
}
```

Common pseudo-elements:

- `::before`
- `::after`
- `::first-letter`
- `::first-line`
- `::selection`
- `::placeholder`

---

## 17. CSS Transitions

Transitions make property changes happen smoothly.

```css
button {
    background-color: blue;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: red;
}
```

Important properties:

- `transition-property`
- `transition-duration`
- `transition-timing-function`
- `transition-delay`

---

## 18. CSS Transforms

Used to rotate, scale, move, or skew elements.

```css
div {
    transform: translate(20px, 10px);
}
```

Common transformations:

```css
transform: rotate(45deg);
transform: scale(1.5);
transform: translateX(20px);
transform: translateY(20px);
transform: skew(10deg);
```

---

## 19. CSS Animations

Animations allow elements to change styles over time.

```css
@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}

.box {
    animation: move 2s infinite alternate;
}
```

Important properties:

- `animation-name`
- `animation-duration`
- `animation-delay`
- `animation-iteration-count`
- `animation-direction`
- `animation-timing-function`
- `animation-fill-mode`

---

## 20. CSS Shadows

### Box Shadow

Adds a shadow around an element.

```css
div {
    box-shadow: 5px 5px 10px gray;
}
```

### Text Shadow

Adds a shadow to text.

```css
h1 {
    text-shadow: 2px 2px 5px gray;
}
```

---

## 21. CSS Opacity and Visibility

### Opacity

Controls transparency.

```css
div {
    opacity: 0.5;
}
```

Values range from `0` (fully transparent) to `1` (fully opaque).

### Visibility

Controls whether an element is visible.

```css
div {
    visibility: hidden;
}
```

**Difference:**
- `display: none` – Removes the element from the layout.
- `visibility: hidden` – Hides the element but preserves its layout space.
- `opacity: 0` – Makes it transparent but preserves its layout space.

---

## 22. CSS Responsive Design

Responsive design makes webpages adapt to different screen sizes.

### Media Queries

```css
.container {
    width: 80%;
}

@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Common breakpoints (examples, not fixed rules):

- Mobile: Up to 480px.
- Tablet: 481px–768px.
- Laptop: 769px–1024px.
- Desktop: Above 1024px.

### Min and Max Width

```css
.container {
    width: 100%;
    max-width: 1200px;
    min-width: 300px;
}
```

### Responsive Units

```css
.container {
    width: 90%;
    font-size: 2rem;
    min-height: 100vh;
}
```

---

## 23. CSS Variables

Variables allow you to reuse values throughout a stylesheet.

```css
:root {
    --primary-color: blue;
    --font-size: 20px;
}

h1 {
    color: var(--primary-color);
    font-size: var(--font-size);
}
```

- `:root` – Selects the document's root element.
- `--variable-name` – Declares a CSS custom property.
- `var()` – Uses a custom property.

---

## 24. CSS Specificity

Specificity determines which CSS rule takes priority when multiple rules target the same element.

General priority:

1. Inline styles.
2. ID selectors.
3. Class, attribute, and pseudo-class selectors.
4. Element and pseudo-element selectors.

Example:

```css
p {
    color: red;
}

.text {
    color: blue;
}

#heading {
    color: green;
}
```

If all three selectors target the same element, the ID selector wins.

### !important

Overrides normal declarations in the cascade.

```css
p {
    color: red !important;
}
```

Avoid using `!important` unnecessarily.

---

## 25. Useful CSS Functions

```css
.container {
    width: calc(100% - 40px);
    width: min(100%, 1200px);
    width: max(50%, 300px);
    width: clamp(300px, 80%, 1200px);
}
```

| Function | Purpose |
|---|---|
| `calc()` | Performs calculations |
| `min()` | Returns the smallest value |
| `max()` | Returns the largest value |
| `clamp()` | Sets a minimum, preferred, and maximum value |
| `var()` | Uses CSS variables |
| `rgb()` | Defines RGB colors |
| `rgba()` | Defines RGB colors with alpha |
| `url()` | References an external resource |

---

## 26. Quick Revision

| Concept | Property / Value |
|---|---|
| Text color | `color` |
| Background | `background-color` |
| Font size | `font-size` |
| Font family | `font-family` |
| Width | `width` |
| Height | `height` |
| Outer spacing | `margin` |
| Inner spacing | `padding` |
| Border | `border` |
| Rounded corners | `border-radius` |
| Display | `display` |
| Position | `position` |
| Stacking order | `z-index` |
| Flexbox | `display: flex` |
| Grid | `display: grid` |
| Text alignment | `text-align` |
| Overflow | `overflow` |
| Transparency | `opacity` |
| Shadow | `box-shadow` |
| Transition | `transition` |
| Animation | `animation` |
| Responsive design | `@media` |
| Transform | `transform` |

---

**Remember:**

- HTML defines the structure of a webpage.
- CSS controls its appearance and layout.
- JavaScript adds interactivity and behaviour.

Learn selectors, the box model, positioning, Flexbox, and Grid particularly well before moving on to JavaScript.

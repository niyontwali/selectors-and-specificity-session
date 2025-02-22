# CSS Selectors and Specificity

CSS (Cascading Style Sheets) is used to style HTML elements. To apply styles, we use **selectors** to target elements in different ways. This document explains common CSS selectors and their specificity.

---

## 1. Element Selector
The **element selector** targets all instances of a specific HTML tag.

### Example:
#### HTML:
```html
<body>
  <p>This is a paragraph.</p>
</body>
```
#### CSS:
```css
body {
  background-color: gray;
}
p {
  color: red;
  font-size: 24px;
}
```
### Explanation:
- The `body` selector changes the background color of the entire page to gray.
- The `p` selector applies red text color and a font size of 24px to all `<p>` elements.

---

## 2. Class Selector
The **class selector** targets elements with a specific class attribute. It is defined using a dot (`.`) before the class name.

### Example:
#### HTML:
```html
<p class="paragraph">This text will be blue.</p>
```
#### CSS:
```css
.paragraph {
  color: blue;
}
```

### Explanation:
- Any element with `class="paragraph"` will have blue text.

---

## 3. ID Selector
The **ID selector** targets an element with a specific `id` attribute. It is defined using a `#` before the ID name.

### Example:
#### HTML:
```html
<p id="paragraphId">This text will be blueviolet.</p>
```
#### CSS:
```css
#paragraphId {
  color: blueviolet;
}
```

### Explanation:
- An element with `id="paragraphId"` will have a blueviolet text color.

---

## 4. Attribute Selector
The **attribute selector** targets elements based on their attributes and values.

### Example:
#### HTML:
```html
<input type="email" placeholder="Enter your email">
```
#### CSS:
```css
input[type="email"] {
  border: 2px solid red;
}
```

### Explanation:
- This targets all `<input>` elements where `type="email"` and applies a red border.

---

## 5. Descendant Selector
The **descendant selector** targets elements that are nested inside a specified parent.

### Example:
#### HTML:
```html
<div>
  <h1>This heading inside a div will be red.</h1>
</div>
```
#### CSS:
```css
div h1 {
  color: red;
}
```

### Explanation:
- This applies a red text color to all `<h1>` elements inside a `<div>`.

---

## CSS Specificity and Priority
CSS rules follow a specificity hierarchy when multiple styles apply to an element:

1. **Inline Styles** (highest priority, written directly in the HTML element)
2. **ID Selectors** (`#idName`)
3. **Class Selectors** (`.className`)
4. **Element Selectors** (`tagName`)

Additionally, the `!important` keyword overrides all other rules.

### Example:
#### HTML:
```html
<p id="mainText" class="text" style="color: green;">This text will be gray because of !important.</p>
```
#### CSS:
```css
#mainText {
  color: blue;
}

p {
  color: gray !important;
}

.text {
  color: purple;
}
```

### Explanation:
- `#mainText` targets an element with `id="mainText"` and sets its color to blue.
- `p` elements are forced to be gray because of `!important`.
- `.text` targets elements with class `text`, but since `!important` is used in the `p` selector, it takes precedence.

---

### Summary of Selector Priorities
| Selector Type     | Priority (1 = Highest) |
|------------------|----------------------|
| Inline Style     | 1 |
| ID Selector (`#id`) | 2 |
| Class Selector (`.class`) | 3 |
| Element Selector (`tag`) | 4 |
| `!important` keyword | Overrides all |

By understanding these selectors and their priorities, you can effectively style your web pages! 🚀


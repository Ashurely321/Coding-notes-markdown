# CSS Notes

This section covers the fundamentals and practical patterns of CSS for styling web pages. It includes syntax, selectors, layout techniques, responsive design, and pro tips for clean, maintainable code.

Each topic is chunked for copy-paste workflow and includes beginner-friendly examples. No icons, no clutter—just focused, actionable reference.

Topics include:

- Selectors (`id`, `class`, pseudo-classes, pseudo-elements)
- Layout (flexbox, grid, positioning)
- Styling (colors, typography, spacing)
- Responsive design (media queries, units)
- Best practices and pro tips

## Selecting by ID

```css
#header {
  background-color: lightgray;
}
```

- `#id`: Targets a unique element with a specific `id`
- Use sparingly—`id` should be unique per page
- Higher specificity than class selectors

## Selecting by Class

```css
.card {
  border: 1px solid #ccc;
  padding: 1rem;
}
```

- `.class`: Targets all elements with the same `class`
- Reusable across multiple elements
- Lower specificity than `id` selectors

## When to Use ID vs Class

```html
<div id="main-header" class="header large"></div>
```

- Use `id` for one-off elements (e.g. main container, modal)
- Use `class` for styling groups of elements (e.g. buttons, cards)
- You can combine both for styling and JS targeting

## Specificity Tips

```css
/* ID selector */
#nav {
}

/* Class selector */
.nav {
}

/* Element selector */
nav {
}
```

- Specificity order: `id` > `class` > `element`
- Avoid overly specific selectors unless necessary
- Use consistent naming to reduce conflicts

## Pseudo-Classes

### Hover

```css
button:hover {
  background-color: #333;
  color: white;
}
```

- Applies when the user hovers over an element
- Great for interactive feedback on buttons, links, etc.

### Focus

```css
input:focus {
  outline: 2px solid blue;
}
```

- Applies when an element receives keyboard or mouse focus
- Important for accessibility and form usability

### Active

```css
a:active {
  color: red;
}
```

- Applies while an element is being clicked
- Often used for links or buttons during press

### First Child

```css
li:first-child {
  font-weight: bold;
}
```

- Targets the first child of a parent element
- Useful for styling lists or navigation menus

### Last Child

```css
li:last-child {
  font-style: italic;
}
```

- Targets the last child of a parent element
- Can be used for spacing or emphasis

### nth-child

```css
tr:nth-child(even) {
  background-color: #f2f2f2;
}
```

- Targets elements based on their position
- Accepts `even`, `odd`, or numeric formulas like `3n+1`

---

### Pro Tips

- Pseudo-classes are dynamic—based on user interaction or element position
- Combine with class selectors for scoped styling
- Use `:focus-visible` for keyboard-only focus styles

## Pseudo-Elements

### ::before

```css
.card::before {
  content: "★ ";
  color: gold;
}
```

- Inserts content before the element’s actual content
- Commonly used for decorative symbols or labels
- Requires `content` property to render

### ::after

```css
.card::after {
  content: " ✓";
  color: green;
}
```

- Inserts content after the element’s actual content
- Great for status indicators or visual cues
- Also requires `content` to display

### Styling First Line

```css
p::first-line {
  font-weight: bold;
  color: navy;
}
```

- Targets only the first line of a paragraph
- Useful for emphasis in long text blocks

### Styling First Letter

```css
p::first-letter {
  font-size: 2rem;
  color: crimson;
}
```

- Targets the first letter of a block element
- Often used for drop caps or stylized intros

---

### Pro Tips

- Pseudo-elements are part of the element but don’t exist in the DOM
- Combine with classes for scoped styling
- Use `::` (double colon) for modern syntax—single `:` still works for legacy support

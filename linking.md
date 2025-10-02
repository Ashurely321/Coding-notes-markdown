# Linking Notes

This section covers how to link content within and across web pages using HTML. It includes anchor tags, external resource linking, navigation techniques, and best practices for accessibility and performance.

Each topic is chunked for copy-paste workflow and includes beginner-friendly examples. No icons, no clutter—just focused, actionable reference.

Topics include:

- Anchor tags (`<a>`) and external links
- Opening links in new tabs securely
- Linking stylesheets, scripts, and favicons
- Internal navigation with fragment IDs
- Best practices and pro tips

## Linking Basics

### Anchor Tag

```html
<a href="https://example.com">Visit Example</a>
```

- `href`: Destination URL or path
- Text between tags is the clickable label
- Can link to external sites, internal pages, or files

### Opening in a New Tab

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer"
  >Visit Example</a
>
```

- `target="_blank"`: Opens link in a new tab
- `rel="noopener noreferrer"`: Improves security and performance

## Linking External Resources to HTML

### Linking a CSS Stylesheet

```html
<link rel="stylesheet" href="styles.css" />
```

- Place inside `<head>`
- `rel="stylesheet"` tells the browser it's a CSS file
- `href` is the path to your `.css` file

### Linking a JavaScript File

```html
<script src="script.js" defer></script>
```

- Place before `</body>` or inside `<head>` with `defer`
- `defer` ensures script runs after HTML is parsed
- Use `type="module"` for ES6 modules if needed

### Linking a Favicon

```html
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

- Place inside `<head>`
- Can use `.ico`, `.png`, or `.svg` formats
- Optional `sizes` attribute for multiple resolutions

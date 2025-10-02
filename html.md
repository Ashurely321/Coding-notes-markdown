# HTML Notes

This section covers the structure and semantics of HTML for building accessible, well-organized web pages. It includes tags, attributes, forms, layout containers, and interactive elements, with practical examples and pro tips for real-world use.

Each topic is chunked for copy-paste workflow and includes beginner-friendly explanations. No icons, no clutter—just focused, actionable reference.

Topics include:

- HTML basics and semantic tag overview
- Common attributes (`id`, `class`, `aria-*`)
- Forms, inputs, and validation patterns
- Layout containers and interactive elements
- Accessibility roles and best practices

# HTML Basics

**HTML (HyperText Markup Language)**
is the skeleton of every webpage. It defines structure, semantics, and content.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Page Title</title>
    <link rel="stylesheet" href="styles.css" />
    <script src="script.js" defer></script>
  </head>
  <body>
    <!-- Page content goes here -->
  </body>
</html>
```

## Semantic Tags Overview

Semantic HTML uses meaningful tags to describe the structure and purpose of content. This improves accessibility, SEO, and code clarity.

| Tag         | Purpose                            | Common Use Case                    |
| ----------- | ---------------------------------- | ---------------------------------- |
| `<header>`  | Introductory content or navigation | Site logo, nav bar, page title     |
| `<main>`    | Primary content of the document    | Article body, dashboard, app logic |
| `<section>` | Thematic grouping of content       | FAQ block, feature list            |
| `<article>` | Self-contained content             | Blog post, news item               |
| `<aside>`   | Tangential or supplementary info   | Sidebar, tips, related links       |
| `<footer>`  | Closing content or metadata        | Copyright, contact info, nav links |

### Pro Tips

- Use only one `<main>` per page—never nest it.
- `<section>` should include a heading (`<h2>`–`<h6>`) to define its theme.
- Prefer semantic tags over generic `<div>`s when possible.
- Screen readers use semantic structure to navigate efficiently.

## Common HTML Attributes

Attributes add extra meaning or behavior to HTML elements. They go inside the opening tag and follow this format: `name="value"`.

| Attribute    | Purpose                                     | Example Usage                                         |
| ------------ | ------------------------------------------- | ----------------------------------------------------- |
| `id`         | Unique identifier for one element           | `<div id="hero-banner">`                              |
| `class`      | Reusable styling or scripting hook          | `<p class="intro-text">`                              |
| `alt`        | Text alternative for images (accessibility) | `<img src="logo.png" alt="Site logo">`                |
| `title`      | Tooltip text on hover                       | `<abbr title="HyperText Markup Language">HTML</abbr>` |
| `role`       | ARIA role for accessibility                 | `<nav role="navigation">`                             |
| `tabindex`   | Controls keyboard navigation order          | `<button tabindex="0">Click Me</button>`              |
| `aria-label` | Custom label for screen readers             | `<button aria-label="Close modal">×</button>`         |

### Pro Tips

- Use `id` for JavaScript targeting or anchor links—never duplicate it.
- Use `class` for styling multiple elements consistently.
- Always include `alt` text for images unless they’re decorative (`alt=""`).
- ARIA attributes like `role` and `aria-label` help screen readers interpret your layout.

## Media & Embeds

### Images

```html
<img
  src="path/to/image.jpg"
  alt="Descriptive text"
  loading="lazy"
  width="300"
  height="200"
/>
```

- `alt`: Required for accessibility and screen readers
- `loading="lazy"`: Defers loading until image is in viewport
- `width` & `height`: Prevent layout shift

### Responsive Images

```html
<picture>
  <source srcset="image.webp" type="image/webp" />
  <source srcset="image.jpg" type="image/jpeg" />
  <img src="fallback.jpg" alt="Descriptive text" />
</picture>
```

- `<picture>`: Enables format switching and responsive sources
- `srcset`: Used with `media` or `type` attributes for flexibility

### Video

```html
<video src="video.mp4" controls width="640" height="360" poster="thumbnail.jpg">
  Your browser does not support the video tag.
</video>
```

- `controls`: Adds play/pause UI
- `poster`: Thumbnail shown before playback
- Optional: `autoplay`, `loop`, `muted`, `preload`

### Audio

```html
<audio src="audio.mp3" controls>
  Your browser does not support the audio tag.
</audio>
```

- `controls`: Adds play/pause UI
- Optional: `autoplay`, `loop`, `muted`

### Embeds & Iframes

```html
<iframe
  src="https://example.com"
  width="800"
  height="600"
  title="Descriptive title"
  loading="lazy"
></iframe>
```

- `title`: Required for accessibility
- `loading="lazy"`: Improves performance
- Avoid using `iframe` for layout—use sparingly for external content

### Object & Embed (rarely used)

```html
<object data="file.pdf" type="application/pdf" width="600" height="400">
  PDF preview not supported.
</object>
```

```html
<embed
  src="file.swf"
  type="application/x-shockwave-flash"
  width="600"
  height="400"
/>
```

- `<object>` is preferred over `<embed>` for fallback content
- Use only when `<iframe>` or native tags aren't viable

---

### Pro Tips

- Always provide fallback text inside `<video>`, `<audio>`, and `<object>` for unsupported browsers
- Use `alt` text that describes function, not just appearance
- Avoid autoplay unless muted—it's disruptive and often blocked
- Prefer `<picture>` and `srcset` for responsive image handling
- Use `iframe` only when necessary—consider alternatives for embedding content

## Form Elements

Forms collect user input and send data to a server or script. Use semantic tags and accessible attributes to ensure usability for all users.

| Element      | Purpose                  | Example Usage                              |
| ------------ | ------------------------ | ------------------------------------------ |
| `<form>`     | Wraps all form controls  | `<form action="/submit" method="POST">`    |
| `<label>`    | Describes an input field | `<label for="email">Email:</label>`        |
| `<input>`    | Single-line input field  | `<input type="text" id="email">`           |
| `<textarea>` | Multi-line text input    | `<textarea rows="4" cols="50"></textarea>` |
| `<select>`   | Dropdown menu            | `<select><option>One</option></select>`    |
| `<option>`   | Item in a dropdown       | `<option value="1">One</option>`           |
| `<button>`   | Clickable action         | `<button type="submit">Send</button>`      |
| `<fieldset>` | Groups related controls  | `<fieldset><legend>Contact Info</legend>`  |
| `<legend>`   | Title for a fieldset     | `<legend>Contact Info</legend>`            |

### Pro Tips

- Always pair `<label>` with `for="id"` to link it to its input.
- Use `type="email"`, `type="tel"`, etc. for built-in validation.
- Group related fields with `<fieldset>` for better accessibility.
- Use `aria-label`, `aria-describedby`, or `aria-invalid` for enhanced screen reader support.

## ARIA Roles and Accessibility

ARIA (Accessible Rich Internet Applications) roles help screen readers understand the purpose of elements, especially when native HTML semantics aren’t enough.

| Role            | Purpose                                | Common Use Case                         |
| --------------- | -------------------------------------- | --------------------------------------- |
| `banner`        | Site-wide header                       | `<header role="banner">`                |
| `navigation`    | Navigation links                       | `<nav role="navigation">`               |
| `main`          | Primary content area                   | `<main role="main">`                    |
| `complementary` | Supporting content                     | `<aside role="complementary">`          |
| `contentinfo`   | Footer or metadata                     | `<footer role="contentinfo">`           |
| `form`          | Group of input controls                | `<form role="form">`                    |
| `button`        | Interactive button                     | `<div role="button">`                   |
| `dialog`        | Modal or popup window                  | `<div role="dialog" aria-modal="true">` |
| `alert`         | Important message that interrupts flow | `<div role="alert">`                    |

### Pro Tips

- Use ARIA roles only when native HTML tags don’t convey the correct meaning.
- Avoid redundant roles (e.g., `<nav role="navigation">` is fine, but `<button role="button">` is unnecessary).
- Combine ARIA roles with attributes like `aria-label`, `aria-labelledby`, and `aria-describedby` for clarity.
- Test with screen readers or accessibility tools to ensure roles behave as expected.

## Form Validation Patterns

HTML offers built-in validation features to ensure users enter correct and complete data. These patterns improve UX and reduce reliance on JavaScript.

| Attribute     | Purpose                              | Example Usage                                |
| ------------- | ------------------------------------ | -------------------------------------------- |
| `required`    | Prevents form submission if empty    | `<input type="text" required>`               |
| `minlength`   | Sets minimum character count         | `<input type="text" minlength="5">`          |
| `maxlength`   | Sets maximum character count         | `<input type="text" maxlength="20">`         |
| `pattern`     | Regex pattern for custom validation  | `<input type="text" pattern="[A-Za-z]{3,}">` |
| `type`        | Triggers browser-specific validation | `<input type="email">`                       |
| `step`        | Controls numeric input increments    | `<input type="number" step="0.5">`           |
| `min` / `max` | Sets numeric or date boundaries      | `<input type="date" min="2025-01-01">`       |
| `novalidate`  | Disables browser validation on form  | `<form novalidate>`                          |

### Pro Tips

- Use `type="email"`, `type="url"`, and `type="tel"` for automatic format checks.
- Combine `pattern` with `title` to explain expected input to users.
- Use `aria-invalid="true"` and `aria-describedby` for accessible error messaging.
- Always test validation behavior across browsers and screen readers.

## Layout Containers

Use layout containers to group, style, and position elements on the page. While `<div>` and `<span>` are non-semantic, they’re essential for layout control—especially with CSS and JavaScript.

| Element     | Type        | Purpose                                 | Example Usage                 |
| ----------- | ----------- | --------------------------------------- | ----------------------------- |
| `<div>`     | Block-level | Generic container for layout or logic   | `<div class="card-wrapper">`  |
| `<span>`    | Inline      | Generic inline container                | `<span class="highlight">`    |
| `<section>` | Block-level | Thematic grouping with semantic meaning | `<section class="features">`  |
| `<article>` | Block-level | Self-contained content                  | `<article class="blog-post">` |
| `<aside>`   | Block-level | Supplementary content                   | `<aside class="sidebar">`     |

### Pro Tips

- Use `<div>` for layout scaffolding, but prefer semantic tags when possible.
- Use `<span>` for inline styling or scripting—never for block-level layout.
- Combine layout containers with Flexbox or Grid for responsive design.
- Keep class names descriptive and consistent to maintain clarity across your CSS and JS.

## Interactive Elements

HTML includes built-in interactive elements that respond to user actions without needing JavaScript. These are great for accessibility and progressive enhancement.

| Element     | Purpose                              | Example Usage                                     |
| ----------- | ------------------------------------ | ------------------------------------------------- |
| `<button>`  | Clickable action                     | `<button type="submit">Send</button>`             |
| `<details>` | Expandable/collapsible content       | `<details><summary>More info</summary></details>` |
| `<summary>` | Label for `<details>` toggle         | `<summary>More info</summary>`                    |
| `<dialog>`  | Modal window                         | `<dialog open>Welcome!</dialog>`                  |
| `<a>`       | Hyperlink to another page or section | `<a href="/about">About Us</a>`                   |
| `<input>`   | User input field                     | `<input type="text">`                             |
| `<select>`  | Dropdown menu                        | `<select><option>One</option></select>`           |

### Pro Tips

- Use `<details>` and `<summary>` for FAQs, spoilers, or expandable sections.
- `<dialog>` requires scripting for full control—use `showModal()` in JS to open it.
- Always include `href` in `<a>` tags—even if using JavaScript for navigation.
- Combine interactive elements with ARIA attributes for better screen reader support.

# DevTools Notes

This section covers how to use browser developer tools to inspect, debug, and optimize web pages. It focuses on Chrome DevTools but applies broadly to other browsers with similar panels and workflows.

Each topic is chunked for copy-paste workflow and includes beginner-friendly explanations. No icons, no clutter—just focused, actionable reference.

Topics include:

- Inspecting elements and editing live HTML/CSS
- Using the Console for logging and debugging
- Breakpoints, scope inspection, and runtime variables
- Network tab for performance and API calls
- Accessibility checks and layout debugging

## Inspecting Elements

### Open DevTools

- Right-click any element on the page and choose **Inspect**
- Or press `Ctrl+Shift+I` (Windows) or `Cmd+Option+I` (Mac)

### HTML Panel

- Shows the live DOM structure of the page
- Hover over elements to highlight them on the page
- Click to expand nested elements and view children

### CSS Styles Panel

- Shows applied styles for the selected element
- You can edit values live and see changes instantly
- Inherited styles are shown lower in the panel

### Box Model

- Visualizes `margin`, `border`, `padding`, and `content` dimensions
- Located at the bottom of the Styles panel
- Useful for debugging layout and spacing issues

---

### Pro Tips

- Use the **Select Element** tool (top-left icon) to click directly on any part of the page
- Changes made in DevTools are temporary—refreshing the page resets them
- You can copy modified HTML or CSS directly from the panel for reuse

## Using the Console

### Open Console

- Press `Esc` to toggle the Console while DevTools is open
- Or click the **Console** tab directly

### Logging Output

```javascript
console.log("Hello, DevTools!");
```

- Displays messages, variables, and debugging info
- Use `console.log()` to trace code execution
- Other methods: `console.warn()`, `console.error()`, `console.table()`

### Viewing Errors

- JavaScript errors appear automatically in the Console
- Click error messages to jump to the source file and line
- Stack traces help identify where the issue originated

### Evaluating Code

- Type JavaScript directly into the Console and press Enter
- Useful for testing expressions, inspecting variables, or triggering functions
- You can access page elements using `$0` (last selected element)

---

### Pro Tips

- Use `console.table()` for readable object and array output
- Filter messages by type (log, warning, error) using the toolbar
- Clear the Console with the trash icon or `Ctrl+L`

## Sources Tab

### Purpose

- View and debug JavaScript files loaded by the page
- Set breakpoints, step through code, and inspect scope
- Explore file structure of the site (HTML, CSS, JS, assets)

### Navigating Files

- Left panel shows file tree grouped by domain
- Click any `.js`, `.css`, or `.html` file to open it
- Use `Ctrl+P` (Windows) or `Cmd+P` (Mac) to quickly search files

### Setting Breakpoints

- Click the line number in a `.js` file to set a breakpoint
- Execution will pause when that line runs
- Use the play/pause and step buttons to control flow

### Scope & Call Stack

- Right panel shows current variables and their values
- Call stack shows the chain of function calls leading to the breakpoint
- Hover over variables to inspect live values

---

### Pro Tips

- Use conditional breakpoints by right-clicking a line number
- You can edit and save local overrides for CSS and JS
- Combine with Console to test variables during paused execution

## Layout Debugging

### Elements Panel: Box Model

- Shows `margin`, `border`, `padding`, and `content` visually
- Hover over each layer to highlight it on the page
- Useful for diagnosing spacing and alignment issues

### Computed Styles

- Shows final calculated values for all CSS properties
- Includes inherited styles and browser defaults
- Great for tracing unexpected layout behavior

### Toggle Element State

- Right-click an element → "Force state" → `:hover`, `:focus`, `:active`
- Simulates pseudo-classes without needing interaction
- Useful for testing styles and transitions

### Layout Tab (Chrome-specific)

- Shows Flexbox and Grid overlays
- Highlights container boundaries and alignment
- Use to inspect gaps, alignment, and item flow

---

### Pro Tips

- Use the **Select Element** tool to isolate layout issues visually
- Check for inherited styles or conflicting rules in the Computed tab
- Use Flexbox/Grid overlays to debug responsive layouts
- Combine with Console to test dynamic style changes

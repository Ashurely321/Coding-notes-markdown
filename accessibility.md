# Accessibility Notes

This section covers how to build inclusive, accessible web experiences using semantic HTML, ARIA roles, keyboard navigation, and screen reader support. It emphasizes practical techniques for improving usability for all users, including those with disabilities.

Topics include:
- Semantic HTML and meaningful structure
- ARIA roles, labels, and live regions
- Keyboard navigation and focus management
- Color contrast and visual clarity
- Screen reader behavior and testing strategies

## ARIA Roles and Accessibility  
ARIA (Accessible Rich Internet Applications) roles help screen readers understand the purpose of elements, especially when native HTML semantics aren’t enough.

| Role             | Purpose                                      | Common Use Case                          |
|------------------|----------------------------------------------|------------------------------------------|
| `banner`         | Site-wide header                             | `<header role="banner">`                 |
| `navigation`     | Navigation links                             | `<nav role="navigation">`                |
| `main`           | Primary content area                         | `<main role="main">`                     |
| `complementary`  | Supporting content                           | `<aside role="complementary">`           |
| `contentinfo`    | Footer or metadata                           | `<footer role="contentinfo">`            |
| `form`           | Group of input controls                      | `<form role="form">`                     |
| `button`         | Interactive button                           | `<div role="button">`                    |
| `dialog`         | Modal or popup window                        | `<div role="dialog" aria-modal="true">`  |
| `alert`          | Important message that interrupts flow       | `<div role="alert">`                     |

### Pro Tips  
- Use ARIA roles only when native HTML tags don’t convey the correct meaning.  
- Avoid redundant roles (e.g., `<nav role="navigation">` is fine, but `<button role="button">` is unnecessary).  
- Combine ARIA roles with attributes like `aria-label`, `aria-labelledby`, and `aria-describedby` for clarity.  
- Test with screen readers or accessibility tools to ensure roles behave as expected.
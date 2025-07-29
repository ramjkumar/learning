[`Front-End Development (HTML, CSS, JS)`](#front-end-development-html-css-js)🔸
[`UI/UX Design`](#uiux-design)🔸
[`Component-Based Development`](#component-based-development)🔸
# Front-End Development (HTML, CSS, JS)
### How do you ensure responsiveness in your UI designs?
I use media queries, fluid grids, and flexible layouts with CSS Flexbox/Grid. Tools like Chrome DevTools help test responsiveness across breakpoints.
### How do you optimize performance in JavaScript-heavy applications?
Debouncing events, lazy loading, splitting code via Webpack, avoiding DOM reflows, and using vanilla JS when appropriate
___
# UI/UX Design
### How do you maintain visual consistency and accessibility across components?
1. **Design system & component library**
  - Use a design system (e.g., Material Design, Carbon Design, or custom) to define visual and functional guidelines.
  - Create a centralized component library (React, Vue, etc.) with reusable, accessible components.
    - **Best Practices**
    - Consistent use of spacing, typography, colors, and iconography.
    - Shared tokens/variables (via SCSS, CSS custom properties, or design tokens via tools like Style Dictionary).
    - Components like Button, Modal, Input, Tooltip, etc., should follow the same patterns and accessibility rules
2. **Accessibility-First Development**
- Follow WCAG 2.1/2.2 guidelines from the start.
- Use semantic HTML elements whenever possible.
- Ensure ARIA is used only when needed and correctly.
  - **Best Practices**
  - Proper heading hierarchy (``<h1>`` to ``<h6>``).
  - Use ``<button>``, ``<nav>``, ``<main>``, ``<section>`` rather than generic ``<div>``
  - All interactive elements must be keyboard accessible.
  - Focus management and skip links for navigation.
___
# Component-Based Development
### What is component-based architecture in frontend development?
Component-based architecture divides UI into independent, reusable pieces (components) that manage their own state. Frameworks like React, Vue, and Angular use this approach. It promotes maintainability, reusability, and testability.
### How do you approach component-based architecture?
I break down the UI into reusable, self-contained components using frameworks like React or Angular. Each component handles its own styling, logic, and state.
___
# API Integration
### How do you handle REST API integration errors in the UI?
1. Categorize API Errors
- **400** -	Bad Request	- Show specific form input errors
- **401 / 403**	-	Unauthorized / Forbidden	- Redirect to login or show access denied message
- **404**	-	Not Found - 	Show friendly “Not Found” page
- **500+**	-	Server Error	- Show “Something went wrong” message, offer retry
- **Network Errors**	-	No Internet / Timeout	Show offline banner or retry mechanism
2. Display Friendly Error Messages
  
  Avoid showing raw server messages like: "Error 500: Internal Server Error"
Instead, display messages like:
- 🔄 - “Something went wrong. Please try again later.”
- ❌ - “We couldn’t save your changes. Check your internet connection.”
___

# Accessibility & Usability
### What is WCAG
WCAG stands for Web Content Accessibility Guidelines. It is a set of international guidelines developed by the W3C (World Wide Web Consortium) to make web content more accessible to people with disabilities.
### Purpose of WCAG
To ensure that websites, apps, and digital content are usable by everyone, including people with:
- Visual impairments (e.g., blindness, low vision, color blindness)
- Hearing impairments
- Mobility/motor disabilities
- Cognitive or learning disabilities
### WCAG Principles – POUR
WCAG is built around four main principles:
- **Perceivable**	Content must be presented in ways users can perceive (e.g., text alternatives for images, captions for videos).
- **Operable**	Users must be able to navigate and interact (e.g., via keyboard, screen readers).
- **Understandable**		Content must be readable and predictable (e.g., clear language, consistent UI).
- **Robust**		Content must work well with assistive technologies (e.g., screen readers, magnifiers).
### WCAG Versions
- **WCAG 2.0** Published 2008	> Widely adopted, formal standard (ISO)
- **WCAG 2.1** Published 2018	> Adds support for mobile, low vision, cognitive disabilities
- **WCAG 2.2** Published 2023	> Adds new success criteria like focus appearance, dragging movements
- **WCAG 3.0 (draft)** Coming soon	>More flexible, broader in scope
### WCAG Conformance Levels
Each guideline has testable success criteria, divided into three levels:
- **A**	- Minimum accessibility	- Provide text alternatives for images
- **AA** - Mid-range, legal requirement in many countries -Ensure good contrast, keyboard navigation
- **AAA**	- Highest level, not always achievable	- Provide sign language interpretation for videos.

Most organizations aim for **WCAG 2.1 AA** compliance as the standard.

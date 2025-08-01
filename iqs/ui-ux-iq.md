[`HTML`](html.md)🔸
[`CSS`](css.md)🔸
[`JS`](js.md)🔸
[`UI/UX Design`](#uiux-design)🔸
[`Component-Based Development`](#component-based-development)🔸
[`State Management`](#state-management)🔸
[`API Integration`](#api-integration)🔸
[`Accessibility & Usability`](#accessibility--usability)🔸
[`Agile/Scrum`](#agilescrum-methodology)🔸
[`Visual Scripting`](#visual-scripting--no-codelow-code)🔸

# UI/UX Design
### ❓ What are the key principles of good UI/UX design?
- **Clarity**: Avoid ambiguity, maintain visual hierarchy.
- **Consistency**: Reuse styles/components.
- **Feedback**: Users should get clear responses from the system.
- **Accessibility**: Follow WCAG to ensure inclusivity.
- **Responsiveness**: Ensure UI works across devices and breakpoints.

### ❓ What is the difference between a wireframe and a prototype?
<table border="1" cellpadding="8" cellspacing="0">
  <thead>
    <tr>
      <th>Feature</th>
      <th>Wireframe</th>
      <th>Prototype</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Fidelity</strong></td>
      <td>Low</td>
      <td>Medium to High</td>
    </tr>
    <tr>
      <td><strong>Design</strong></td>
      <td>Simple layout, no color or styling</td>
      <td>Detailed visuals, branding, UI elements</td>
    </tr>
    <tr>
      <td><strong>Interactivity</strong></td>
      <td>None or minimal (like navigation flow)</td>
      <td>Clickable, simulates real interactions</td>
    </tr>
    <tr>
      <td><strong>Purpose</strong></td>
      <td>Define structure and layout</td>
      <td>Test functionality and user experience</td>
    </tr>
    <tr>
      <td><strong>Tools</strong></td>
      <td>Balsamiq, Sketch, Figma (low-fi)</td>
      <td>Figma, Adobe XD, InVision (interactive)</td>
    </tr>
      <tr>
      <td><strong>Example</strong></td>
      <td>Sketching how the homepage of a website will be structured: where the logo, menu, banner, and content sections will go.</td>
      <td>Demonstrating how a user would sign up for an account or add an item to a cart in a mobile app.</td>
    </tr>
  </tbody>
</table>

### ❓ What is user-centered design and how do you implement it?
User-Centered Design is an iterative design process in which designers focus on the users and their needs in each phase of the design process. It involves users throughout to ensure that the final product is highly usable and meets their expectations.

**Key Principles of UCD**:
- **Focus on Users and Tasks**
    - Understand who the users are, what they want, and how they behave.
- **Empirical Measurement**
    - Use observations, usability testing, and data to drive decisions.
- **Iterative Design**
    - Continuously refine the design based on feedback and testing.
- **Involvement of Users**
    - Engage real users early and often throughout the process.
 
**The UCD Process (Step-by-Step)**:
1. Research & Understand the Users
    - Methods: User interviews, Surveys, Personas, Empathy maps, Task analysis
    - Goal: Build a deep understanding of user goals, pain points, and contexts.
2. Define User Requirements
    - Document user needs and convert them into design requirements.
    - Use user stories and use cases to describe what users need to achieve.
3. Design Solutions
    - Create wireframes, prototypes, and user flows.
    - Focus on accessibility, usability, and consistency.
    - Tools: Figma, Sketch, Adobe XD, Balsamiq.
4. Evaluate & Test
    - Conduct usability testing with real users.
    - Techniques: A/B testing, Heuristic evaluation, Screen reader or keyboard-only navigation testing (for accessibility), Analyze results and identify usability issues.
5. Refine & Iterate
    - Improve the design based on feedback and re-test.
    - Loop through design and test phases until goals are met.
  
### ❓ How do you maintain visual consistency and accessibility across components?
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
### ❓ What is component-based architecture in frontend development?
Component-based architecture divides UI into independent, reusable pieces (components) that manage their own state. Frameworks like React, Vue, and Angular use this approach. It promotes maintainability, reusability, and testability.
### ❓ How do you approach component-based architecture?
I break down the UI into reusable, self-contained components using frameworks like React or Angular. Each component handles its own styling, logic, and state.
### ❓ How do you avoid unnecessary re-renders in a component?
- Use React.memo, useMemo, useCallback.
- Avoid changing object references unnecessarily.
- Split into smaller components.
___
# State Management
### ❓ Explain global vs local state with example.
Local state belongs to a specific component (e.g., modal open/close). Global state is shared (e.g., user authentication info). Global state is managed via Redux, Vuex, or Context API.
### ❓ When would you use global vs local state?
- **Local State**: Form inputs, toggle UI states.
- **Global State**: User auth, theme, API data.
### ❓ What state management tools have you used and why?
write answer here...
### ❓ How would you manage state in a medium to large app?
write answer here...
___
# API Integration
### ❓ How do you consume a REST API in vanilla JavaScript?
write answer here...
### ❓ How do you handle API errors and loading states in the UI?
write answer here...
### ❓ How do you handle REST API integration in a scalable frontend app?
I use fetch or axios for API calls, centralize logic in services, implement proper loading/error states, and cache frequent responses using state management libraries like Redux or Vuex.
### ❓ How do you handle API errors in frontend?
- Show user-friendly error messages
- Use try...catch
- Retry logic for transient errors
```
try {
  const response = await fetch('/api/data');
  if (!response.ok) throw new Error('API Error');
  const data = await response.json();
} catch (err) {
  console.error(err);
  showToast("Failed to load data.");
}

```
### ❓ How do you handle REST API integration errors in the UI?
1. ✅ Categorize API Errors
    - **400** -	Bad Request	- Show specific form input errors
    - **401 / 403**	-	Unauthorized / Forbidden	- Redirect to login or show access denied message
    - **404**	-	Not Found - 	Show friendly “Not Found” page
    - **500+**	-	Server Error	- Show “Something went wrong” message, offer retry
    - **Network Errors**	-	No Internet / Timeout	Show offline banner or retry mechanism
2. ✅ Display Friendly Error Messages
    - Avoid showing raw server messages like: "Error 500: Internal Server Error"
    - Instead, display messages like:
    - 🔄 - “Something went wrong. Please try again later.”
    - ❌ - “We couldn’t save your changes. Check your internet connection.”
 
3. ✅ Retry Logic for Transient Errors
    - Use retry mechanisms for timeouts or 5xx errors.
    - Implement exponential backoff for automated retries (e.g., using libraries like axios-retry).

4. ✅ Global Error Handling with Interceptors
    - Centralize your error-handling logic for consistency.

5. ✅ UX Practices
    - Loading indicators during API calls to indicate progress.
    - Disable submit buttons to prevent duplicate API calls.
    - Auto-recover UI if possible (e.g., auto-refresh token and retry).
    - Form field-specific errors when validation fails (from a 400 response).

6. ✅ Logging and Monitoring
    - Log errors (to console or to a monitoring service like Sentry).
    - Provide detailed logs for devs, but user-friendly messages in UI.
___
# Accessibility & Usability
### ❓ What is WCAG
WCAG stands for Web Content Accessibility Guidelines. It is a set of international guidelines developed by the W3C (World Wide Web Consortium) to make web content more accessible to people with disabilities.

**Purpose of WCAG**

To ensure that websites, apps, and digital content are usable by everyone, including people with:
- Visual impairments (e.g., blindness, low vision, color blindness)
- Hearing impairments
- Mobility/motor disabilities
- Cognitive or learning disabilities

**WCAG Principles – POUR**

WCAG is built around four main principles:
- **Perceivable**	Content must be presented in ways users can perceive (e.g., text alternatives for images, captions for videos).
      Ensure that users can perceive the content, regardless of their sensory abilities.
        - Text alternatives: Provide alt text for images, transcripts for audio, and captions for video
        - Semantic HTML: Use proper HTML tags (<header>, <nav>, <main>, <footer>, etc.) to help screen readers interpret content
        - Color contrast: Maintain sufficient contrast between text and background (e.g., WCAG recommends a ratio of at least 4.5:1).
        - Responsive design: Ensure content adapts to various screen sizes and orientations.
        - Content structure: Use headings (<h1> to <h6>) and landmarks to organize content clearly.
- **Operable**	Users must be able to navigate and interact (e.g., via keyboard, screen readers).
- **Understandable**		Content must be readable and predictable (e.g., clear language, consistent UI).
- **Robust**		Content must work well with assistive technologies (e.g., screen readers, magnifiers).

**WCAG Versions**
- **WCAG 2.0** Published 2008	> Widely adopted, formal standard (ISO)
- **WCAG 2.1** Published 2018	> Adds support for mobile, low vision, cognitive disabilities
- **WCAG 2.2** Published 2023	> Adds new success criteria like focus appearance, dragging movements
- **WCAG 3.0 (draft)** Coming soon	>More flexible, broader in scope

**WCAG Conformance Levels**

Each guideline has testable success criteria, divided into three levels:
- **A**	- Minimum accessibility	- Provide text alternatives for images
- **AA** - Mid-range, legal requirement in many countries -Ensure good contrast, keyboard navigation
- **AAA**	- Highest level, not always achievable	- Provide sign language interpretation for videos.

Most organizations aim for **WCAG 2.1 AA** compliance as the standard.

### ❓ How do you ensure your web app is accessible?
 1. ✅ Follow WCAG Guidelines
 2. ✅ Use Semantic HTML
 3. ✅ ARIA Roles and Attributes (when needed)
    - Use ARIA only when semantic HTML isn't sufficient.
    - Use roles like ``role="dialog"`` or ``aria-live="polite"`` appropriately.
    - Avoid unnecessary ARIA like ``role="button"`` on a real ``<button``.
  4. ✅ Keyboard Navigation Support
    - Ensure all functionality is accessible using a keyboard:
    - Use tabindex, focus(), and skip links
    - Custom components should handle keyboard events (Enter, Space, Esc, etc.)
  5. ✅ Color Contrast & Visual Design
  6. ✅ Forms and Labels
  7. ✅ Alt Text for Images
  8. ✅ Test with Assistive Technologies
      - Test using: Screen readers: NVDA, JAWS, VoiceOver
      - Screen magnifiers
      - Keyboard-only navigation
  9. ✅ Automated Accessibility Testing
      - Use tools like: axe DevTools
      - Lighthouse (Chrome DevTools)
      - WAVE, But remember: Automated tools catch ~30–40% of issues.
  10. ✅ Manual and User Testing
  11. ✅ Responsive and Adaptive Layouts
  12. ✅ Accessibility in Components and Frameworks
        
### ❓ What are some common WCAG violations you’ve fixed?
- Missing alt attributes on images
- Improper use of heading tags
- Insufficient color contrast
- Lack of focus states
- Modal dialogs not accessible with keyboard

### ❓ What challenges have you faced with accessibility, and how did you solve them?
Screen reader issues with dynamic content; I resolved them using ARIA live regions and avoiding role conflicts.

### ❓ What is Inclusivity in Accessibility?
Inclusivity in accessibility means creating digital (and physical) products, services, and environments that everyone can use, no matter their abilities, background, or situation.

**Inclusivity in accessibility** = designing for **human diversity** by intentionally supporting different **abilities, cultures, and contexts** — not just complying with accessibility checklists.

**Key Principles of Inclusivity in Accessibility**
- **Equity**: Everyone gets the same quality of experience, even if the methods vary (e.g., screen readers, captions, or alternative navigation).
- **Flexibility**:	Interfaces support different ways of interacting: touch, voice, keyboard, assistive devices.
- **Perception**: Content should be understandable regardless of vision, hearing, or cognitive ability.
- **Adaptability**: Designs respond to user preferences (dark mode, text size, language).
- **Empathy**: Consider users' lived experiences during the design and testing process.
  
**Examples**
- **Accessibility**: Providing alt text for images.
- **Inclusivity**: Writing that alt text in a way that conveys meaning and cultural sensitivity.
- **Accessibility**: Ensuring all actions are keyboard accessible.
- **Inclusivity**: Designing navigation that's intuitive for someone new to technology.

**Benefits of Inclusive Accessibility**
- Better user experience for everyone, not just people with disabilities.
- Increased market reach (older adults, people in low-bandwidth areas, etc.).
- Legal and ethical alignment (ADA, Section 508, WCAG).
- Encourages innovation through diverse perspectives.

### ❓ Legal and ethical alignment in accessibility
Legal and ethical alignment in accessibility ensures that digital products and services are usable by all people, including individuals with disabilities. This involves adhering to laws, regulations, and standards that promote equal access. In most countries, legal and ethical accessibility practices revolve around three core frameworks:
1. ✅**Americans with Disabilities Act (ADA)**

- 🔹**What is ADA?**
    - The Americans with Disabilities Act (1990) is a U.S. civil rights law that protects people with disabilities from discrimination in jobs, schools, transportation, and public places.

- 🔹**How ADA applies to Digital Accessibility**:
    - Although the original ADA doesn’t explicitly mention websites or digital content, courts and the Department of Justice (DOJ) have increasingly interpreted it to apply to websites, mobile apps, and digital services.
 
- 🔹**Key Legal Considerations**:
    - Applies to Title II (state and local governments) and Title III (public accommodations like businesses).
    - Websites that are not accessible (e.g., not usable with screen readers or keyboard-only navigation) can be seen as a barrier—which is discriminatory under ADA.
    - Lawsuits have risen against businesses, schools, hospitals, etc., for ADA violations.

- 🔹**Ethical Relevance**:
    - ADA supports the equal dignity and rights of people with disabilities.
    - Ethically, it's about inclusion and nondiscrimination.
   
2. ✅**Section 508 of the Rehabilitation Act**
   
- 🔹**What is Section 508?**
    - Section 508 is a U.S. federal law that requires federal agencies to make their electronic and information technology (EIT) accessible to people with disabilities.

- 🔹**Scope**
    - Applies to federal websites, systems, documents, and software.
    - Any vendors or contractors working with federal agencies must also comply.
    - Introduced in 1998, and updated in 2018 (508 Refresh) to align with WCAG 2.0 Level AA.

- 🔹**Compliance Requirement**
    - All federal EIT must meet WCAG 2.0 Level AA success criteria (as of 2018).
    - Applies to web content, software, PDFs, videos, and other digital assets.
   
- 🔹**Legal Implications**
    - Noncompliance can result in contract penalties, procurement disqualification, or civil actions.
   
- 🔹**Ethical Relevance**
    - Public services should be equitably accessible to all taxpayers.
    - Ensures equal opportunity in employment and information access.

3. ✅**Web Content Accessibility Guidelines (WCAG)**

### ❓ What is the difference between ARIA roles and native HTML elements?
write answer here...
### ❓ How do you make forms accessible?
write answer here...
### ❓ How do you test your site for accessibility compliance?
write answer here...
___
# Agile/Scrum Methodology
### ❓ How do you contribute to Agile ceremonies?
In sprint planning, I help estimate UI tasks with story points; in daily standups, I report blockers; and during retros, I suggest improvements in collaboration.
### ❓ Describe your experience working in Agile teams.
I've worked in 2-week sprint cycles. I participate in daily standups, sprint planning, demos, and retrospectives. I ensure design tickets are refined ahead, prioritize UI bugs, and sync regularly with QA and backend devs for smooth integration. I use tools like Jira or Azure Boards for managing user stories and tasks.
### ❓ What is your role in a daily standup?
write answer here...
### ❓ How do you handle mid-sprint changes?
write answer here...
### ❓ Explain your workflow in a typical sprint.
write answer here...
___
# Visual Scripting & No-Code/Low-Code
### ❓ What is no-code automation?
No-code automation enables building workflows using visual tools. I've used Zapier to trigger notifications on form submissions and Power Automate to connect SharePoint and Outlook for task automation.
### ❓ What is your experience with visual scripting tools?
I’ve used Mendix and OutSystems to build UI workflows with drag-and-drop interfaces and custom logic blocks.
### ❓ How do low-code platforms impact UI/UX quality?
They speed up development but need design governance to avoid inconsistency. I standardize layouts and enforce design tokens across templates.
### ❓ What experience do you have with no-code platforms?
I’ve built internal tools using [e.g. Bubble] where I used visual workflows to automate tasks like form submission, notifications, and report generation. I integrated with REST APIs for dynamic data.
### ❓ What low-code platforms have you worked with?
write answer here...
### ❓ How do you automate workflows without writing code?
write answer here...
### ❓ How do you use tools like Power Automate or Zapier?
write answer here...

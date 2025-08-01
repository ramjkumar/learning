### HTML

### ❓ How do you implement responsive design?
1. ✅ Use a Responsive Meta Tag
   - ``` <meta name="viewport" content="width=device-width, initial-scale=1.0"> ```
2. ✅ Use Fluid Layouts with Relative Units
   - % for widths
   - em, rem for spacing and font sizes
   - vw, vh for viewport-based sizing
3. ✅ Apply CSS Media Queries
4. ✅ Use Flexbox and Grid for Layouts
5. ✅ Make Images and Media Responsive
   ```
   img, video {
     max-width: 100%;
     height: auto;
   }
    ```
6. ✅ Mobile-First Design Approach
7. ✅ Test Across Devices and Viewports
   - Browser DevTools (Chrome, Firefox) with device emulators
   - Real devices for hands-on testing
   - Tools like BrowserStack or Responsively App

### ❓ What is the purpose of ARIA roles in HTML?
The purpose of **ARIA (Accessible Rich Internet Applications)** roles in HTML is to improve accessibility for users who rely on assistive technologies like screen readers.

**Key Purposes of ARIA Roles**:
1. ✅ Describe non-native HTML elements:
   - ARIA roles help describe the function or purpose of custom or complex UI components (like sliders, modals, tabs) that are not natively accessible.
   - Example: If you create a custom button using a ``<div>``, a screen reader won’t recognize it as a button unless you add:
      - ``` <div role="button" tabindex="0">Click me</div> ```
2. ✅ Enhance semantic meaning:
   - ARIA roles add semantic information to elements that do not provide it by default. This allows assistive technologies to interpret the UI more accurately.   
3. ✅ Enable rich interactions:
   - Modern web apps often use JavaScript-heavy interactions. ARIA allows you to communicate the dynamic state (e.g., expanded, selected, disabled) to users who can’t perceive visual cues.
      - ``` <button aria-expanded="false" aria-controls="menu">Menu</button> ```
4. ✅ Improve navigation for screen readers:
   - ARIA landmark roles (like `` role="navigation", role="main", role="banner" ``) help users navigate quickly through regions of the page.

**ARIA Roles Examples**:
- **button** -	Identifies an element as a button
- **dialog** -	Marks a modal dialog
- **navigation** -Defines a navigation section
- **tab** -	Identifies a tab in a tablist
- **tooltip** - Describes a tooltip element

### ❓ What is the difference between inline and block elements?
- **Block Elements**
   - Always start on a new line.
   - Take up the full width available (by default).
   - Can contain other block or inline elements.
   - You can set width, height, margin, and padding.
   - ``` <div>, <p>, <h1> to <h6>, <ul>, <ol>, <li>, <section>, <article> ```
- **Inline Elements**
   - Do not start on a new line.
   - Only take up as much width as necessary.
   - Can contain text or other inline elements only.
   - You can set horizontal padding/margin, but not width/height directly (unless using CSS like display: inline-block).
   - ``` <span>, <a>, <strong>, <em>, <img>, <label>, <abbr> ```
 
### ❓ How do you optimize images for web use
1. Choose the Right File Format
2. Resize Images Appropriately
   - Generate multiple sizes for responsive images using **srcset**
   - ```
     <img src="image-600.jpg"
     srcset="image-400.jpg 400w,
             image-600.jpg 600w,
             image-1000.jpg 1000w"
     sizes="(max-width: 600px) 100vw, 600px"
     alt="Description of image">
      ```
   - Compress Images
   - Use Lazy Loading
      - ``` <img src="image.jpg" loading="lazy" alt="..." /> ```
   - Implement Image CDN
      - Cloudflare Images, Imgix, Cloudinary, ImageKit
   - Leverage Browser Caching
   - Use CSS Sprites for Icons
      - Use SVG sprites or icon fonts (like Font Awesome) where possible.
   - Audit with Tools
      - Google PageSpeed Insights
      - Lighthouse (Chrome DevTools)
      - WebPageTest.org
      - GTmetrix

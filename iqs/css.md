# CSS
### Box model in CSS?
The Box Model in CSS is a fundamental concept that describes how elements on a web page are structured and how space is allocated around them. Every HTML element is considered a box, and the CSS Box Model defines how the size of that box is calculated.

**Components of the CSS Box Model**
Each box consists of four layers (from inside out):
- **Content**: The actual content of the element (text, image, etc.).
- **Padding**: The space between the content and the border. It increases the size of the box but not the content area.
- **Border**: A line surrounding the padding (if any) and content. You can set its width, style, and color.
- **Margin**: The space outside the border that separates the element from other elements.

**box-sizing Property**
- content-box (Default)
    - Width and height include only the content.
    - Padding and border are added outside the content area.
-  border-box
    - Width and height include content + padding + border.
    - This makes layout more predictable.
```
div {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 10px solid black;
  box-sizing: content-box;
}
```
**Rendered size**
- content-box > Width = 200 (content) + 40 (padding) + 20 (border) = 260px
- border-box > Width = 200px total (content shrinks to fit padding + border inside)

### How do you handle performance in large-scale CSS?
I use methodologies like BEM(Block Element Modifier) for scalable class naming, CSS variables for reuse, and critical CSS loading to prioritize above-the-fold content. I also avoid large nested selectors and leverage code-splitting where supported.

### Explain how Flexbox and Grid differ.
write answer here...

### How do you optimize CSS for performance?
write answer here...

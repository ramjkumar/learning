# CSS
### ❓ Box model in CSS?
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

### ❓ CSS Combinators
1. **Descendant Combinator (space)**
    - Selects all elements that are descendants (children, grandchildren, etc.) of a specified element.
    - ```
      div p {
      color: blue;
        }
        ```
2. **Child Combinator (>)**
    - Selects only direct child elements of a specified element.
    - ```
        div > p {
          color: green;
        }
      
        <div>
          <p>This is green.</p>
          <section>
            <p>This is not green.</p> <!-- Not a direct child of div -->
          </section>
        </div>
        ```

3. **Adjacent Sibling Combinator (+)**
    - Selects the first element that is immediately next to a specified element.
    - ```
          h2 + p {
              font-weight: bold;
            }
        
        <h2>Title</h2>
        <p>This paragraph is bold.</p>
        <p>This one is not affected.</p>    
      ```
4. **General Sibling Combinator (~)**
    - Selects all siblings of an element that come after it (not just the first one).
    - ```
      h2 ~ p {
          color: red;
        }

      <h2>Header</h2>
        <p>This is red.</p>
        <p>This is also red.</p>
      ```

### ❓ How do you handle performance in large-scale CSS?
I use methodologies like BEM(Block Element Modifier) for scalable class naming, CSS variables for reuse, and critical CSS loading to prioritize above-the-fold content. I also avoid large nested selectors and leverage code-splitting where supported.

### ❓ Explain how Flexbox and Grid differ.
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Feature</th>
      <th><strong>Flexbox</strong></th>
      <th><strong>Grid</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Layout Direction</strong></td>
      <td>One-dimensional (either row <strong>or</strong> column)</td>
      <td>Two-dimensional (rows <strong>and</strong> columns)</td>
    </tr>
    <tr>
      <td><strong>Use Case</strong></td>
      <td>Best for aligning items in a single direction</td>
      <td>Best for full page or complex component layouts</td>
    </tr>
    <tr>
      <td><strong>Item Placement</strong></td>
      <td>Items placed sequentially along main axis</td>
      <td>Items can be placed anywhere via row/column lines</td>
    </tr>
    <tr>
      <td><strong>Responsiveness</strong></td>
      <td>Easy for simple, linear responsive layouts</td>
      <td>More powerful for complex, responsive grid layouts</td>
    </tr>
  </tbody>
</table>


### ❓ How do you optimize CSS for performance?
write answer here...

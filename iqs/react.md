## 1. What is strict mode in React?
It is a useful component for highlighting potential problems in an application. Just like <Fragment>, <StrictMode> does not render any extra DOM elements. It activates additional checks and warnings for its descendants. These checks apply for development mode only. It has no impact on the production build. 
## 2. What is the Virtual DOM and how does React use it for performance optimization?
The Virtual DOM (VDOM) is a lightweight, in-memory representation of the real DOM. It’s one of React’s most powerful features for improving performance and efficiency.

Instead of updating the browser’s real DOM directly (which is slow), React creates a virtual copy of it in memory. When a component’s state or props change:

1. React creates a new Virtual DOM tree.


2. It compares the new tree with the previous one using a process called diffing.


3. It finds the minimal set of changes needed to update the real DOM.


4. Only those specific parts are re-rendered — making React fast and efficient.

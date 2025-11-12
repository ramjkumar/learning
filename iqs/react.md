### ❓ What is strict mode in React?
It is a useful component for highlighting potential problems in an application. Just like `<Fragment>`, `<StrictMode>` does not render any extra DOM elements. It activates additional checks and warnings for its descendants. These checks apply for development mode only. It has no impact on the production build. 
### ❓ What is the Virtual DOM and how does React use it for performance optimization?
The Virtual DOM (VDOM) is a lightweight, in-memory representation of the real DOM. It’s one of React’s most powerful features for improving performance and efficiency.

Instead of updating the browser’s real DOM directly (which is slow), React creates a virtual copy of it in memory. When a component’s state or props change:

- React creates a new Virtual DOM tree.
- It compares the new tree with the previous one using a process called diffing.
- It finds the minimal set of changes needed to update the real DOM.
- Only those specific parts are re-rendered — making React fast and efficient.

**Example**:

When you update a counter: `setCount(count + 1)`

React doesn’t re-render the entire UI.
It only updates the element where count is displayed — thanks to the Virtual DOM diffing algorithm.

**Advantages**:

- Faster UI updates
- Efficient rendering
- Better performance compared to direct DOM manipulation
### ❓ Adjacent JSX Elements Must Be Wrapped In An Enclosing Tag 
Use fragment to wrap the two component. You are returning two elements simultaneously which causes that error 
### ❓ Component composition
Component composition is a fundamental concept in React that allows us to build complex UIs by combining smaller, independent components. 
It provides the following advantages:
- **Reusability**: components can be reused
- **Maintainability**: easier to update and manage the code
- **Improved Readability**: Smaller, focused components are easier to understand and debug 
```js
const Header = () => <h1>Welcome !< /h1>; 
const Content = () => <p>This is the main content .< /p>; 
const Footer = () => <small>@ 2025</small>; 
const Page = () => ( 
  <div> 
    <Header /> 
    <Content /> 
    <Footer /> 
  </div> )
  ```
### ❓ Conditional rendering
Rendering UI based on the condition
### ❓ Why index should not be used as key in for loop or map 
- When we have components at same level and if a new component comes without ID, DOM will re-render all components again, as DOM can't identify where to place it. 
- But if we give unique ID, react knows where to put that component according to the ID. It is good for optimization and performance.
### ❓ What is React Fiber, and how is it different from the old React reconciliation algorithm?
React Fiber is the core reconciliation engine introduced in React 16 — a complete rewrite of React’s rendering architecture. Its main goal is to make React’s rendering process incremental, interruptible, and prioritized, allowing smoother user experiences and better control over rendering performance.

Before Fiber, React used a stack-based reconciliation algorithm that was synchronous and non-interruptible. Once rendering started, React couldn’t stop until it finished updating the entire tree — often leading to frame drops or unresponsive UIs during large updates.

**How React Fiber Works**:

React Fiber breaks the rendering process into small units of work (called “fibers”) and assigns priority levels to them. It can pause, reuse, or discard work depending on what’s happening in the app.

- Each Fiber node represents a unit of work for a React element.
- React can pause work on low-priority updates to handle urgent ones (like user input).
- Once the high-priority task finishes, React resumes the paused work without starting over.

**Key Differences from Legacy Stack**:

In older versions, React performed recursive synchronous rendering, blocking the main thread. Fiber introduced a linked-list structure that enables React to manage work asynchronously. This makes it possible to:

- Implement features like Concurrent Rendering and Suspense.
- Improve performance for large component trees.
- Optimize rendering for better responsiveness.

**Real-World Analogy**: 
Think of React Fiber as a multitasking system — it can juggle multiple tasks at once, prioritize the most important ones, and ensure the app stays smooth and snappy.

**In Short**:
React Fiber = The foundation that made React concurrent, responsive, and future-proof

### ❓ What is Concurrent Mode in React, and how does it improve user experience?

Concurrent Mode (introduced experimentally in React 18) is a set of new rendering capabilities that allow React to work on multiple UI updates simultaneously, making applications more responsive and fluid — even during heavy computations.

In traditional React (pre-Fiber), rendering was synchronous and blocking. If one large update was in progress, React couldn’t handle other interactions (like button clicks or typing) until that update finished. Concurrent Mode solves this by making rendering interruptible and concurrent.

**How It Works**:

React breaks rendering into chunks and schedules them with priorities.

If a high-priority event (like user input) occurs, React pauses the current render to handle it first.

Once the important task is done, React resumes the pending render from where it left off — without restarting.

**Key Benefits**:

- **No UI Freezes**: The page remains interactive, even during large re-renders.
- **Adaptive Rendering**: React adjusts automatically based on device performance.
- **Smooth Transitions**: Enables seamless data fetching and page updates using features like useTransition().
- **Better Perceived Performance**: Users see updates faster, improving UX.

**Example**: If your app is rendering a complex list while a user types in a search box, Concurrent Mode ensures the input stays responsive, instead of lagging or freezing.

**In Short**: Concurrent Mode = The brain behind React’s non-blocking, priority-based, and super-smooth rendering

### ❓ What is Reconciliation in React and how does it work under the hood?

Reconciliation is the core algorithm React uses to efficiently update the DOM when the component’s state or props change. It determines what exactly needs to change in the UI instead of re-rendering everything.

When something changes in your app, React creates a new Virtual DOM tree and compares it to the previous one — this process is called Diffing. React then applies the minimal number of real DOM changes needed to make the UI match the latest Virtual DOM.

**How It Works**:
- React builds a new Virtual DOM tree when data changes.
- It compares (diffs) this new tree with the old one.
- If an element’s type is the same, React updates its attributes and keeps its child structure.
- If an element’s type differs, React removes the old one and mounts a new DOM node.
- Finally, it batches updates for better performance.

**Example**: If only one `<li>` in a list changes, React will update just that `<li>` — not the entire list.

**Key Concept**: Reconciliation ensures React apps stay fast, responsive, and efficient by minimizing unnecessary DOM operations.

### ❓ What are React Hooks and why are they used?

React Hooks are special functions introduced in React 16.8 that allow you to use state and lifecycle features in functional components — without writing class components.

They make code simpler, cleaner, and more reusable by letting you “hook into” React features directly.

**Common Hooks**:

- **useState()** → Manages state in functional components.
- **useEffect()** → Handles side effects (like fetching data or updating the DOM).
- **useContext()** → Accesses context values without using props drilling.
- **useRef()** → Accesses or stores mutable values that persist between renders.
- **useMemo()** & **useCallback()** → Optimize performance by memoizing values or functions.

**Example**:
  ```
  import React, { useState } from 'react';
  
  function Counter() {
   const [count, setCount] = useState(0);
   return (
   <button onClick​={() => setCount(count + 1)}>
   Count: {count}
   </button>
   );
  }
  ```

Here, useState manages the count state in a functional component.

### ❓ What is the difference between Virtual DOM and Real DOM?

The Virtual DOM is a lightweight copy of the Real DOM that React uses to improve rendering performance.

In the Real DOM, every time something changes in the UI, the entire DOM structure gets updated — which is slow.
React instead updates a Virtual DOM, compares it with the previous version (called diffing), and only updates the changed parts in the Real DOM.

**Key Points**:
- Virtual DOM is faster and more efficient.
- Real DOM is slower because it directly updates the UI.
- Virtual DOM improves performance by reducing unnecessary re-renders.

**Example**: When you change state in React, only the affected components re-render — not the entire page.

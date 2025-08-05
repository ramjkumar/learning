# JS

## ⏩ Fundamentals
  
### ❓ Hoisting
- Hoisting is JavaScript's default behavior of moving declarations to the top.
- During JS code execution, memory is allocated to all variables and function during memory creation phase.
- Variables will be allocated undefined before initialization, function will hold the entire function code
  -  Variable can be used before it has been declared

### ❓ Temporal Dead Zone
- Time between hoisting and initialization. It happens with let & const.
- Before initialization if we try to access, we will get Reference error – cannot access variable name before initialization

 ### ❓ Lexical Environment
 During JS code execution, memory is allocated to all variables and function during memory creation phase, along with this lexical environment is also created, which is nothing but reference to outer function / higher level until it reaches the global scope 

### ❓ What is the difference between var, let, and const?
1. **var**
    - **Scope**: Function-scoped.
    - **Hoisting**: Hoisted to the top of the function or global scope. Initialized with undefined.
    - **Re-declaration**: Allowed within the same scope.
    - **Usage**: Old way of declaring variables (before ES6).
        - ```
          function example() {
          console.log(x); // undefined
          var x = 10;
          console.log(x); // 10
        }
          ```
2. **let**
    - **Scope**: Block-scoped (inside {}).
    - **Hoisting**: Hoisted but not initialized, so accessing it before declaration causes a ReferenceError.
    - **Re-declaration**: Not allowed in the same scope.
    - **Usage**: Preferred when variable values need to change.
        - ```
          function example() {
            console.log(x); // ReferenceError
            let x = 10;
          }
          ```
3. **const**
    - **Scope**: Block-scoped (like let).
    - **Hoisting**: Same as let (hoisted but not initialized).
    - **Re-declaration**: Not allowed.
    - **Assignment**: Must be initialized when declared and cannot be reassigned.
    - **Mutation**: You can change contents of objects or arrays declared with const, but can't reassign the variable itself.
        - ```
          const x = 5;
          x = 10; // ❌ TypeError
          
          const arr = [1, 2];
          arr.push(3); // ✅ Allowed: array is mutated, not reassigned
          ```

### ❓ What is the difference between null, undefined & not defined ?
- **null** - A variable has been explicitly assigned "no value"
  - ```
    let b = null;
    console.log(b); // null
    ```
- **undefined** - A variable has been declared but not assigned a value
  - ```
    let a;
    console.log(a); // undefined
    ```
- **not defined** - Accessing a variable which is neither defined or declared
  - ```
    let a;
    console.log(b); // not defined
    ```

### ❓ What are the differences between ``==`` and ``===`` in JavaScript?
- ``==`` compares values after type coercion.
- ``===`` compares both value and type.
```
'5' == 5  // true
'5' === 5 // false
```

## ⏩ Data Manipulation

### ❓ How to empty an array in JavaScript?
`` var arrayList =  ['a','b','c','d','e','f']; ``
- **Method 1** `` arrayList = [] ``
- **Method 2** `` arrayList.length = 0 ``
- **Method 3** `` arrayList.splice(0, arrayList.length) ``
- **Method 4**
  ```
    while(arrayList.length){
    arrayList.pop();
  }
  ```

### ❓ Reverse string
``` let revStr = str.split('').reverse().join(''); ```

## ⏩ DOM & Event Handling

### ❓ What is event delegation in JavaScript?
Event delegation in JavaScript is a technique where instead of attaching event listeners to individual child elements, you attach a single event listener to a common parent element. This listener can monitor events from its children by taking advantage of event bubbling (where events propagate from the target element up through its ancestors).

**How It Works**
When an event occurs on a child element, it bubbles up to its ancestors. You can catch that event on a parent element and use the event.target to figure out which child triggered it.

**Why Use Event Delegation?**
- **Performance**: Reduces the number of event listeners in the DOM.
- **Dynamic Content**: Works well when child elements are added or removed dynamically.
- **Cleaner Code**: Centralizes event logic in one place.

```
<ul id="menu">
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>

<script>
  document.getElementById('menu').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
      alert('You clicked: ' + event.target.textContent);
    }
  });
</script>
```

## ⏩ Performance Optimization

### ❓ How do you optimize performance in JavaScript-heavy applications?
Debouncing events, lazy loading, splitting code via Webpack, avoiding DOM reflows, and using vanilla JS when appropriate

## ⏩ Control Flow & Execution

### ❓ Event loop
Event loop is a fundamental concept in JS that enables asynchronous programming despite JS being single threaded. which allows JS to run tasks like timers, web requests and user actions without stopping the entire program

**How the Event Loop Works**
1. **Call Stack**: JavaScript uses a call stack to manage function execution. When a function is called, it’s added to the stack, and when it returns, it’s removed from the stack. 
2. **Web APIs**: Functions like setTimeout, fetch, and DOM events are handled by the browser’s Web APIs, which operate outside the call stack.
3. **Callback/Task Queue**: When Web APIs complete their tasks, they push their callbacks to the callback queue (setimeout, console, dom apis)
4. **Micro task queue** - All the callback functions which comes through promises (fetch) & Mutation observer 
5. **Event Loop**: The event loop continuously checks the call stack and the callback queue. If the call stack is empty, it moves the first callback from the queue to the stack for execution.

```
console.log('Start');
setTimeout(() => {
  console.log('Timeout');
}, 0);
console.log('End'); 
```
**Explanation**
- **Synchronous Code**: console.log('Start') and console.log('End') are synchronous and are executed immediately, in order.
- **Asynchronous Code**: setTimeout is asynchronous. It sets a timer and the callback is placed in the callback queue after the timer expires (0 milliseconds in this case).
- **Event Loop**: The event loop checks the call stack. Once the synchronous code is executed and the stack is empty, it processes the callback queue, executing the setTimeout callback. 

This mechanism allows JavaScript to handle asynchronous operations efficiently, ensuring that the main thread is not blocked by long-running tasks 

### ❓ Difference Between Promise and Async/Await
A **Promise** is an object that represents the eventual completion (or failure) of an asynchronous operation.
- A Promise is a way to handle asynchronous operations.
- It represents a value that might be available now, later, or never.
- You use ``.then()`` to get the result and ``.catch()`` to handle errors.
    - ```
      fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => console.log(data))
      .catch(error => console.error('Error:', error));
      ```

**Async/Await** in JS provide a modern syntax for writing asynchronous code, making it appear more synchronous and easier to read and manage compared to traditional callback functions or explicit Promise chaining.
- ```
  async function getData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
    } catch (error) {
      console.error('Error:', error);
    }
  }
  ```

## ⏩ Uncategorized

### ❓ shallow copy vs deep copy in javascript
In JavaScript, shallow copy and deep copy refer to how objects (or arrays) are duplicated, especially when they contain nested structures. Here's a breakdown of the differences:
- **Shallow Copy**
  - A shallow copy duplicates only the top-level properties of an object. If the object contains nested objects or arrays, the references to those nested structures are copied—not the actual values.
    - ```
      const original = {
        name: "Ram",
        address: { city: "Chennai", pin: 600001 }
      };
      
      const shallowCopy = { ...original };
      
      shallowCopy.name = "Kumar";
      shallowCopy.address.city = "Bangalore";

      console.log(original.name); // Output: "Ram"
      console.log(original.address.city); // Output: "Bangalore"

      ``` 
- **Deep Copy**
  - A deep copy duplicates all levels of the object, including nested objects and arrays. Changes to the copied object do not affect the original.
    - ```
      const original = {
        name: "Ram",
        address: { city: "Chennai", pin: 600001 }
      };
      
      const deepCopy = structuredClone(original);
      
      deepCopy.address.city = "Bangalore";
      
      console.log(original.address.city); // Output: "Chennai"
      ```
    - ```
      const deepCopy = JSON.parse(JSON.stringify(original));
      ```
    - ```
      import _ from 'lodash';
      const deepCopy = _.cloneDeep(original);
      ```
    - ```
      import cloneDeep from 'lodash/cloneDeep';

      const obj = { a: 1, b: { c: 2 } };
      const deepCopy = cloneDeep(obj);
      
      deepCopy.b.c = 6;
      console.log(obj.b.c); // Output: 2
      ```

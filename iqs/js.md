# JS

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

### ❓ What are the differences between ``==`` and ``===`` in JavaScript?
- ``==`` compares values after type coercion.
- ``===`` compares both value and type.
```
'5' == 5  // true
'5' === 5 // false
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

### ❓ What is event delegation in JavaScript?
write answer here...

### ❓ How do you optimize performance in JavaScript-heavy applications?
Debouncing events, lazy loading, splitting code via Webpack, avoiding DOM reflows, and using vanilla JS when appropriate

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

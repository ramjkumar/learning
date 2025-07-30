# JS

### ❓ Hoisting
- Hoisting is JavaScript's default behavior of moving declarations to the top.
- During JS code execution, memory is allocated to all variables and function during memory creation phase.
- Variables will be allocated undefined before initialization, function will hold the entire function code
  -  Variable can be used before it has been declared 

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


### ❓ What is event delegation in JavaScript?
write answer here...

### ❓ How do you optimize performance in JavaScript-heavy applications?
Debouncing events, lazy loading, splitting code via Webpack, avoiding DOM reflows, and using vanilla JS when appropriate

### ❓ Reverse string
``` let revStr = str.split('').reverse().join(''); ```

# JS

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
- **not defined** - Accessing a variable which is neither defined or decalared
  - ```
    let a;
    console.log(b); // not defined
    ```
### ❓ What is event delegation in JavaScript?
write answer here...

### ❓ How do you optimize performance in JavaScript-heavy applications?
Debouncing events, lazy loading, splitting code via Webpack, avoiding DOM reflows, and using vanilla JS when appropriate

### ❓ Reverse string
``` let revStr = str.split('').reverse().join(''); ```

# Copy a function in JavaScript

```js
const newFunction = oldFunction.bind({});
```

- [Function.prototype.bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) creates a new function with `this` set to the value passed in the argument. 
- A new function is created and it references the function that bind was called on.
- The new function will not have references to any additional properties that may have been attached to the original function.

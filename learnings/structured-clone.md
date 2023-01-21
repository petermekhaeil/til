# Deep clone object with structuredClone()

[structuredClone()](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone) is a native API in JavaScript that can do deep cloning of objects:

```js

const original = {
  name: "Peter",
  properties: {
    age: new Date()
  }
};

const copy = structuredClone(original);

copy.properties.action = "Jump";
original.properties.action; // undefined
```

It can handle circular references and other JS built-in types such as `Date`, `Set`, `Map`.

Learn more on [MDN](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone).

## What about object spread?

The object spread operator actually does a shallow copy. If you modify a deeply nested property, both objects are affected:

```js
const original = {
  name: "Peter",
  properties: {
    age: new Date()
  }
};

const copy = { ...original };

copy.properties.action = "Jump";
original.properties.action; // "Jump"
```

# JavaScript Symbol.iterator

[Symbol.iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator) defines the default iterator for an object. Applying it to an object to enable iteration:

```tsx
const myObject = { a: 1, b: 2, c: 3 };

myObject[Symbol.iterator] = function* () {
  for (const key of Object.keys(this)) {
    yield [key, this[key]];
  }
};

for (const [key, value] of myObject) {
  console.log(key, value);
}
```

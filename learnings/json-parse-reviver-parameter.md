# JSON.parse reviver parameter

[JSON.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) has an optional `reviver` parameter that can transform the value being parsed.

This is useful for deserialization:

```js
const jsonString = '{"date":"Sun, 12 Feb 2023 06:45:00 GMT"}';

function reviver(key, value) {
  if (key === "date") {
    return new Date(value);
  }
  return value;
}

const data = JSON.parse(jsonString, reviver);
    // ^? { date: Date }
```

JSON.parse's `reviver` and JSON.stringify's `replacer` can be combined together to build a JSON serialization and deserialization utility.

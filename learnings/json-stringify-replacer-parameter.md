# JSON.stringify replacer parameter

`JSON.stringify` has an optional second parameter [replacer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify#the_replacer_parameter) that can recursively transform properties during the stringify process. 

The `replacer` parameter can be a function or an array:

```js
JSON.stringify({ name: 'Peter', til: true }, ['name']);
// '{"name":"Peter"}'
```

```js
function replacer(key, value) {
  if (key === 'name') {
    return 'Mekhaeil';
  }
  return value;
}

JSON.stringify({ name: 'Peter', til: true }, replacer);
// '{"name":"Mekhaeil","til":true}'
```

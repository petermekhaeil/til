# CSS.escape()

[CSS.escape()](https://developer.mozilla.org/en-US/docs/Web/API/CSS/escape) returns an string that conforms to the CSS selector specs. Useful when generating dynamic CSS selectors based on an input.

```js
CSS.escape("app:@org/name");
// 'app\\:\\@org\\/name'
```

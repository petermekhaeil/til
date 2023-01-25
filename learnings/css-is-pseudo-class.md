# CSS :is() pseudo-class

The [:is](https://developer.mozilla.org/en-US/docs/Web/CSS/:is) pseudo-class takes a list of selectors and selects any elements that matches the selectors in that list. Its useful to compact large selectors. 

Take this example:

```css
header h2,
nav h2,
article h2 {
  color: black;
}
```

Can be written as:

```css
is:(header, nav, article) h2 {
  color: black;
}
```

## Learn More

It's worth noting there is a difference between `:is` and `:where()` when it comes to specificity value. Detailed explanations:

- [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)
- [Simpler CSS Selectors With :is()](https://www.builder.io/blog/css-is)
- [Using :is() in complex selectors selects more than you might initially think](https://www.bram.us/2023/01/17/using-is-in-complex-selectors-selects-more-than-you-might-initially-think/)

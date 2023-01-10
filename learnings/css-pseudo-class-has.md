# CSS :has() pseudo-class

The `:has(<selector>)` pseudo-class selects elements that contain certain child elements that match the `<selector>` selectors.

## Demo

Open the [CodeSandbox](https://pmen4y.csb.app/) demo. The `:has()` selector is being used to select the pricing card that contains a `.popular` element:

```css
.pricing-card:has(.popular) { 
  border-color: blue; 
}
```

## Examples

```css
/* section that contain an image */
section:has(img) {
  color: red;
}

/* section that contain a .sale element */
section:has(.sale) {
  border-color: red;
}

/* section that does NOT contain a .sale element */
section:not(:has(.sale)) {
  border-color: red;
}

/* paragraph that contains an anchor */
p:has(a) {
  color: blue;
}

/* paragraph that contains a an image as first sibling */
p:has(> img) {
  color: blue;
}

/* paragraph that contains a an image as first sibling */
p:has(> img) {
  color: blue;
}

/* h1 that is followed by a paragraph */
h1:has(+ p) { 
  margin-bottom: 0; 
}
```

## Support

See [caniuse.com](https://caniuse.com/?search=has) for browser support.

Can also use CSS to detect if the feature is supported:

```css
@supports(selector(:has(img))) {}
```

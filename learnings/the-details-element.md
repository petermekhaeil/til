# The Details disclosure element

The `<details>` HTML element creates an accordion-like element that the user can toggle open and close.

The [W3C HTML specification](http://www.w3.org/html/wg/drafts/html/master/interactive-elements.html#the-details-element) describes the element:

> The details element represents a disclosure widget from which the user can obtain additional information or controls.

## Usage

```html
<details>
  <summary>Show/Hide</summary>
  <p>Today I learnt about the `details` element</p>
</details>
```

The `open` attribute is a boolean that can be used to indicate if the content is visible or not.

```html
<details open="true">
  <summary>Show/Hide</summary>
  <p>Today I learnt about the `details` element</p>
</details>
```

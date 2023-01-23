# Get current page URL in Astro

[`Astro.url`](https://docs.astro.build/en/reference/api-reference/#astrourl) returns the current page URL from the Request object. The return value is a [URL](https://developer.mozilla.org/en-US/docs/Web/API/URL) object which contains properties like pathname and origin. 

```js
const currentPath = Astro.url.pathname;
```

Useful when you need to highlight navigation links based on current page:

```jsx
<a href="/me" class={currentPath === '/me' ? 'active' : ''}>
  About Me
</a>
```

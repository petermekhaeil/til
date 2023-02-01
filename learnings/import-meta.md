# import.meta

[import.meta](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import.meta) is an object that is available within Javascript ES modules. It contains metadata about the module and is extensible.

It contains `import.meta.url` that returns the full URL of the module.

```html
<script type="module" src="module.mjs"></script>
```

```js
// module.mjs
let img = document.createElement('img');
img.src = new URL('image.jpg', import.meta.url);
document.body.appendChild(img);
```

## Difference from process.env

`process.env` is specific to Node and cannot be used in the browser.

## TypeScript support

```ts
interface ImportMeta {
  myVariable: string
}

import.meta.myVariable; // string
```

## Uses

[Vite](https://vitejs.dev) extend `import.meta` to add things like:
- [Env Variables](https://vitejs.dev/guide/env-and-mode.html#env-variables-and-modes): `import.meta.env`.
- [Glob Import As](https://vitejs.dev/guide/features.html#glob-import-as): `import.meta.glob`

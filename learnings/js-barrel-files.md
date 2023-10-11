# JavaScript Barrel File

A barrel file is a module that re-exports from other modules:

```js
// ./components/index.js
export { Button } from './Button.js';
export { Anchor } from './Anchor.js';
export { Text } from './Text.js'
```

Usage:

```js
import { Button, Anchor, Text } from './components';
```

## Performance Impact

Barrel files have an impact on your bundler performance (this is how I came across the term _Barrel Files_). 

- [Next.js recommend to not use them](https://nextjs.org/blog/next-13-1#import-resolution-for-smaller-bundles).
- They make it difficult on bundlers to analyse your code.  
- They risk exporting modules of the same name.
- They have a chance of circular references.

## Read More

- https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-7/
- https://renatopozzi.me/articles/your-nextjs-bundle-will-thank-you
- https://flaming.codes/posts/barrel-files-in-javascript

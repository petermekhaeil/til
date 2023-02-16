# JavaScript Import Map

An [import map](https://github.com/WICG/import-maps) is JSON that browsers use to resolve the path of JS modules when used in `import` and `import()` statements. 

An example can be found on [three.js](https://threejs.org/docs/#manual/en/introduction/Installation):

```html
<script type="importmap">
  {
    "imports": {
      "three": "https://unpkg.com/three@0.149.0/build/three.module.js"
    }
  }
</script>

<script type="module">
  import * as THREE from 'three';
  const scene = new THREE.Scene();
</script>
```

Another example commonly seen in micro-frontends:

```html
<script type="importmap">
  {
    "imports": {
      "react": "https://unpkg.com/react@18.2.0/umd/react.production.min.js",
      "react-dom": "https://unpkg.com/react-dom@18.2.0/umd/react-dom.production.min.js"
    }
  }
</script>

<script type="module">
  import * as React from 'react';
  import * as ReactDOM from 'react-dom';
</script>
```

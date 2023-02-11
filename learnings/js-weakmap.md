# JavaScript WeapMap

[WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) have "weak" reference to its keys. When the references to the key is lost and there are more references to the value, the value can be garbage collected.

```tsx
const pokemon = { name: "Pikachu" };

const myPokemons = new WeakMap();
myPokemons.set(pokemon, 1);

// reference removed
pokemon = null;

// pokemon is removed from memory
myPokemons.has(pokemon); // false
```

## Map vs WeakMap

- **WeakMap** keys must be objects and cannot be primitives.
- If an object is used in a **Map**, as long as the Map exists, so does that the object.
- **WeakMap** does not have interation methods (`keys()`, `values()`, `entries()`).
- You cannot check the size of a **WeakMap**.

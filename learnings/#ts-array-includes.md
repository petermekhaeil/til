# TypeScript narrow Array.includes()

A common problem faced with using `Array.includes()` in TypeScript:

```tsx
const environments = ["DEV", "UAT", "PROD"] as const;

function isSupported(env: string) {
  if (environments.includes(env)) {
    // Error: Argument of type 'string' is not 
    // assignable to parameter of type '"DEV" | "UAT" | "PROD"'.
  }
}
```

The definition of `Array.includes()`:

```tsx
interface Array<T> {
  includes(searchElement: T, fromIndex?: number): boolean;
}
```

The function wants both the searchElement and the array to be of the same type.

This can be solved by narrowing the type using a helper function:

```tsx
function includes<T extends U, U>(arr: ReadonlyArray<T>, searchElement: U): searchElement is T {
  return arr.includes(searchElement as T);
}
```

- Takes in array of type `ReadonlyArray<T>` and search for element of type `U`.
- `T extends U`: T is a subset of U.
- If condition is true, we narrow using `searchElement is T`.

```tsx
function isSupported(env: string) {
  if (includes(environments, env)) {
    console.log(env);
              // ^? env: "DEV" | "UAT" | "PROD"
  }
}
```

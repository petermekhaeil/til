# Inferring the types from a Remix loader

The `loader` function in [Remix](https://remix.run/) can be inferred automatically using:

```tsx
type LoaderData = Awaited<ReturnType<typeof loader>>;
```

- `Awaited`: Extracts the value returned from a `Promise`.
- `ReturnType`: Constructs a type consisting of the return type of a function.

Putting it together:

```tsx
import { json } from "@remix-run/node"; 

type LoaderData = Awaited<ReturnType<typeof loader>>;
// ^? LoaderData: Response

export const loader = async () => {
  return json({ ok: true });
};
```

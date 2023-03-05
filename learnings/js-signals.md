# Signals

> Signals are reactive primitives for managing application state.

([Reference](https://preactjs.com/guide/v10/signals/))

Signals are **reactive**. They keep track of the subscriptions and notify subscribers when state has changed. Calling the getter creates a subscription, telling the signal of the location that requires the value.

## Signals vs useState()

- `useSignal()` => getter + setter
- `useState()` => value + setter

`useState()` is not reactive. React does not know of the location that requires the value, therefore must re-renders the whole component when calling the setter.

([Reference](https://www.builder.io/blog/usesignal-is-the-future-of-web-frameworks))

## Signals in frameworks

### SolidJS

```jsx
import { createSignal } from "solid-js";

function Counter() {
  const [count, setCount] = createSignal(0);

  setInterval(() => setCount(count() + 1), 1000);

  return <div>Count: {count()}</div>;
}
```

### Qwik

```jsx
export default component$(() => {
  const count = useSignal(0);

  return (
    <>
      <button onClick$={() => count.value++}>Increment</button>
      Count: {count.value}
    </>
  );
});
```

### Preact

```jsx
import { signal } from "@preact/signals";

const count = signal(0);

function Counter() {
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => count.value++}>click me</button>
    </div>
  );
}
```

### Vue

- Vue has a guide on [reactivity](https://vuejs.org/guide/extras/reactivity-in-depth.html#connection-to-signals) that compares signals with Vue's Composition API.
- Evan You [writes Solid style signals in Vue in ~10 lines](https://twitter.com/youyuxi/status/1618181618069573633).
- Evan You [writes Angular style signals in Vue in ~15 lines](https://twitter.com/youyuxi/status/1628214809631293440).

### Angular
 
Angular has [announced](https://github.com/angular/angular/discussions/49090) some prototyping work around adding signals as a reactive primitive in Angular.

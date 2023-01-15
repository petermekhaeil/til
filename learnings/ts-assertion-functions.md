# TypeScript Assertion Functions

Assertion functions throw an error if a certain condition is not met. 

```ts
  // Throw error if `name` is not "Peter"
  assert(name === "Peter");
```

TypeScript's "assertion signatures" are used to narrow the type of values to be more specific.

Consider the below example: We are not sure of the type of `maybeNumber`. We can assert it is a number before continuing with the code flow. 

```ts
function assert(condition: unknown): asserts condition {
  if (!condition) {
    throw new Error("Assertion failed.");
  }
}

let maybeNumber: any;
assert(typeof maybeNumber === "number");

maybeNumber;
  // ^? let maybeNumber: number
```

We can be more specific with the condition. Below example has an assertion signature `asserts value is number`:

```ts
function assertIsNumber(value: unknown): asserts value is number {
  if (typeof value !== "number") {
    throw new Error("Not a number");
  }
}

let maybeNumber: any;
assert(typeof maybeNumber === "number");

maybeNumber;
  // ^? const maybeNumber: number
```

TypeScript's Assertion Functions is how libraries like [tiny-invariant](https://github.com/alexreardon/tiny-invariant) work.

```ts
import invariant from 'tiny-invariant';

invariant(truthyValue, 'This should not throw!');
```

A basic version of this function that includes a custom message to be used as the error message when the assertion fails:

```ts
function assert(condition: unknown, message?: string): asserts condition {
  if (!condition) {
    throw new Error(message || 'Assertion failed.');
  }
}
```

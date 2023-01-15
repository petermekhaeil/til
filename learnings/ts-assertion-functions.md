# TypeScript Assertion Functions

Assertion functions throw an error if a certain condition is not met. 

```ts
assert(name === "Peter");
```

The assertion function will throw an error `name` is not "Peter". 

## Assertion Signatures

With assertion functions, there is "assertion signatures" which are used to narrow the type of values to be more specific.

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

We now know that `maybeNumber` is a number because the assertion did not fail, so TypeScript narrowed the type down to `number.

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
  // ^? let maybeNumber: number
```

## Putting it together

We can also include a custom message to be used as the error message when the assertion fails:

```ts
function assert(condition: unknown, message?: string): asserts condition {
  if (!condition) {
    throw new Error(message || 'Assertion failed.');
  }
}

let myVariable: { myKey: string } | undefined;

myVariable.myKey;
 // ^? 'myVariable' is possibly 'undefined'.

assert(myVariable, "myVariable is undefined");

myVariable
 // ^? let myVariable: { myKey: string } 
```

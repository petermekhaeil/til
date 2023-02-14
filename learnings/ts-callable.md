# TypeScript: Callable interface

Adding an interface for callable objects:

```tsx
interface Callable {
  (): string;
}

const myCallable: Callable = function () {
  return "I was called";
};

const myFunction = myCallable;
const value = myFunction();
    // ^? const value: string
```

Another example with parameters:

```tsx
interface Callable {
  (numOne: number, numTwo: number): number;
}

const addNumbers: Callable = function (numOne, numTwo) {
  return numOne + numTwo;
};

const myFunction = addNumbers;
const value = myFunction(1, 2);
    // ^? const value: number
```

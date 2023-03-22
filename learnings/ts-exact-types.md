# TypeScript Exact Types

TypeScript will not show an error if additional keys are added to an object literal:

```ts
type User = {
  name: string;
};

const userData = {
  name: "Peter",
  email: "peter@email.com",
};

function printUser(user: User) {
  console.log(user);
}

printUser({ name: "Peter", email: "peter@email.com" });
// Error: Object literal may only specify known properties, and 'email' does not exist in type 'AllowedType'.

printUser(userData);
// No error on this line
```

This is because it is intentional. See [microsoft/TypeScript#12936](https://github.com/microsoft/TypeScript/issues/12936).

A workaround is available on [https://stackoverflow.com/a/61960616](https://stackoverflow.com/a/61960616) by using a custom utility `Exact`:

```tsx
type Exact<A, B> = A extends B ? (B extends A ? A : never) : never;

type User = {
  name: string;
};

const userData = {
  name: "Peter",
  email: "peter@email.com",
};

function printUser<T>(user: Exact<T, User>) {
  console.log(user);
}

printUser({ name: "Peter", email: "peter@email.com" });
// Error: Object literal may only specify known properties, and 'email' does not exist in type 'AllowedType'.

printUser(userData);
// Error: Argument of type '{ name: string; email: string; }' is not assignable to parameter of type 'never'
```

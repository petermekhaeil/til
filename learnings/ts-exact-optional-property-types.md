# TypeScript: exactOptionalPropertyTypes

TypeScript handles optional and undefined differently - [exactOptionalPropertyTypes](https://www.typescriptlang.org/tsconfig#exactOptionalPropertyTypes) will help catch scenarios where `undefined` should be typed explicitly.

When turned off:

```ts
type User = {
  email?: string;
}

const user: User = { email: undefined }
// Valid
```

When turned on:

```ts
type User = {
  email?: string;
}

const user: User = { email: undefined }
    // Type '{ email: undefined; }' is not assignable to type 'User' with 'exactOptionalPropertyTypes: true'.
    // Consider adding 'undefined' to the types of the target's properties.
```

Read [optional vs undefined | TkDodo's blog](https://tkdodo.eu/blog/optional-vs-undefined) to learn the difference and how this can help.

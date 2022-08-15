# TypeScript: @ts-expect-error

TypeScript allows you to suppress errors on a line by using the `@ts-ignore` directive right before the erroring line:

```ts
// @ts-ignore
const myString: string = 1;
```

The downside to using `@ts-ignore` is that there is no indication if it is really supressing any errors unless the directive is removed. This can lead to forgotten `@ts-ignore` once the errors has been fixed.

Using `@ts-expect-error` will behave the same way but if there is no error in the code, TypeScript will report an error that the `@ts-expect-error` was not necessary:

```ts
// @ts-expect-error
const myString: string = 1;
```

This is a great alternative to `@ts-ignore` if you intend to fix the code at a later stage. When the error is fixed, TypeScript will remind you to remove the directive.

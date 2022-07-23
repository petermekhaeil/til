# TypeScript Config: noUnCheckedIndexAccess

`noUnCheckedIndexAccess` adds `undefined` to any un-declared fields in a type. This is useful if you have an index signature and want to check if a property exists before accessing it.

Take this example:

```ts
const myObject: Record<string, string[]> = {};

myObject["myKey"].push("myString");
```

This satisfies TypeScript because `myKey` is typed as `string` in the index signature of `myObject`. What we do not know yet is if `myObject["myKey"]` is defined for us to use.

With `noUnCheckedIndexAccess` enabled, TypeScript will warn us that the object is possibly `undefined` and that we should check it exists:

```ts
const myObject: Record<string, string[]> = {};

if (myObject["myKey"]) {
  myObject["myKey"].push("myString");
}
```

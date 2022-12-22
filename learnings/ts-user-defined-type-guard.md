# User-defined type guard in TypeScript

Types can be narrowed down by using the `is` keyword:

```ts
const isString = (value: unknown): value is string => {
  return typeof value === 'string';
}

function myFunction(value: string | number) {
  if (isString(value)) {
    value
    // ^? (parameter) value: string
  } else {
    value
    // ^? (parameter) value: number	
  }
}
```

When `isString` is called, TypeScript will narrow the type to `string` if the function returns `true`. TypeScript will also handle the `else` branch and narrows the type to `number` as it now knows that it is not a `string`.

Another example:

```ts
type Color = 'red' | 'blue' | 'green';

function isRed(color: string): color is 'red' {
  return color === 'red'
}

function paint(color: Color) {
  if (isRed(color)) {
    color
    // ^? (parameter) color: "red"
  } else {
    color
    // ^? (parameter) color: "blue" | "green"
  }
}
```

In the example above, `isRed` narrows `color` to `red` if the function returns true, otherwise the type is narrowed to `"blue" | "green"`.

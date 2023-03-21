# Overriding HTML Attributes in React TypeScript

First extend the native HTML attributes:

```ts
interface MyInputProps extends React.HTMLProps<HTMLInputElement> {
  size: "sm" | "md" | "lg";
}
```

A typescript will appear because TS knows that `HTMLInputElement` already has a `size` attribute and it does not match the one we added:

```ts
interface MyInputProps extends React.HTMLProps<HTMLInputElement> {
  size: "sm" | "md" | "lg";
// ^? Type 'string' is not assignable to type 'number'
}
```

We need to omit the native `size` attribute:

```ts
interface MyInputProps extends Omit<React.HTMLProps<HTMLInputElement>, 'size'> {
  size: "sm" | "md" | "lg";
}
```

And now we can type our new component. Spread the props so our new `size` prop is not set as the value to the native HTML attribute.

```ts
const MyInput: React.FC<MyInputProps> = (props) => {
  const { size, ...rest } = props;
  return <input {...rest} className="my-input" />;
};
```

If we want to continue using the native `size`, [Chakra UI](https://chakra-ui.com/docs/components/input/usage#changing-the-size-of-the-input) has a clever technique of using a new prop `htmlSize` that can be used instead:

```ts
interface MyInputProps extends Omit<React.HTMLProps<HTMLInputElement>, 'size'> {
  size: "sm" | "md" | "lg";
  htmlSize?: number;
}

const MyInput: React.FC<MyInputProps> = (props) => {
  const { size, htmlSize, ...rest } = props;
  return <input {...rest} size={htmlSize} className="my-input" />;
};
```

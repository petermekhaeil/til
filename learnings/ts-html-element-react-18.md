# Extending HTML Element Types in React 18

React 18 removed the `children` prop from `React.FC` and must be defined explicitly in your component's type.

When creating new React components that extend HTML elements (eg Button), you will need to specify the `children` prop in React 18:

```tsx
type ButtonProps = React.ButtonHTMLAttributes<HTMLButtonElement> & {
  children: React.ReactNode;
};

const Button: React.FC<ButtonProps> = ({
  children,
  disabled,
  name,
  type,
  value
}) => {
  return (
    <button disabled={disabled} name={name} type={type} value={value}>
      {children}
    </button>
  );
};
```


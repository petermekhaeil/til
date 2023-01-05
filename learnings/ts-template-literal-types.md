# TypeScript Template Literal Types

TypeScript has the ability to add string types using template literal strings:

```ts
type EventType = "Click" | "Change";
type OnEventType = `on${EventType}`
      // ^? type OnEventType = "onClick" | "onChange"
```

It also returns every possible combination of the unions:

```ts

type CssAttr = "margin" | "padding";
type Position = "left" | "right" | "top" | "bottom";
type CssKeys = `${CssAttr}-${Position}`
         // ^? type CssKeys = "margin-left" 
         //                   | "margin-right" 
         //                   | "margin-top" 
         //                   | "margin-bottom" 
         //                   | "padding-left" 
         //                   | "padding-right" 
         //                   | "padding-top"
         //                   | "padding-bottom"
```


Can be used on object keys:

```ts
type Events = {
  [key in `on${string}`]: () => void;
}

const events: Events = {
  onClick: () => {},
  onChange: () => {}
  // ^? ✅ (property) onChange: () => void
  brokenFn: () => {}
  // ^? ❌ Object literal may only specify known properties, and 'brokenFn' does not exist in type 'Events'
}
```

Can be used with the other string manipulation types:

```ts
type Action = 'query' | 'mutation';

type Hook = `use${Capitalize<Actions>}`;
  // ^? type Hook = "useQuery" | "useMutation"
```

Can be used with generics:

```ts
type EventType = "click" | "change";

type OnEventType<T extends string> = {
  [key in T as `on${Capitalize<key>}`]: () => void
}

const events: OnEventType<EventType> = {
  onClick: () => {},
  onChange: () => {},
    // ^? ✅ (property) onChange: () => void
  brokenFn: () => {}
   // ^? ❌ Object literal may only specify known properties, and 'brokenFn' does not exist in type 'OnEventType<EventType>'
}
```

There is also a curated list of [Awesome Template Literal Types on GitHub](https://github.com/ghoullier/awesome-template-literal-types) that is worth checking out for more examples.

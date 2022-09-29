# TypeScript: Exhaustiveness checking in switch with union type

The `never` data type in TypeScript can be used to check that all cases in a switch are considered.

```ts
type Day =
  | "Monday"
  | "Tuesday"
  | "Wednesday"
  | "Thursday"
  | "Friday"
  | "Saturday"
  | "Sunday";

const day = "Monday" as Day;
let result = 0;

switch (day) {
  case "Monday": {
    result = 1;
    break;
  }
  default: {
    // `Type 'string' is not assignable to type 'never'.`
    const exhaustiveCheck: never = day;
    throw new Error(`Unexpected: ${exhaustiveCheck}`);
  }
}
```

`exhaustiveCheck` will have an error because TypeScript is attempting to assign the rest of the `Day` union to `never` which cannot happen.

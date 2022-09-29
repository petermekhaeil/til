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

function getDayIndex(day: Day) {
  switch (day) {
    case "Monday": {
      return 1;
    }
    default: {
      // `Type 'string' is not assignable to type 'never'.`
      const _exhaustiveCheck: never = day;
      return _exhaustiveCheck;
    }
  }
}
```

`_exhaustiveCheck` will have an error because TypeScript is attempting to assign the rest of the `Day` union to `never` which cannot happen.

This can be found in the [TypeScript documentation](https://www.typescriptlang.org/docs/handbook/2/narrowing.html?#exhaustiveness-checking).

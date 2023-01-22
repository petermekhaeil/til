# TypeScript: Type-only imports and exports

TypeScript can enforce explicit type imports and exports using the [importsNotUsedAsValues](https://www.typescriptlang.org/tsconfig#importsNotUsedAsValues) configuration. 

```json
{
  "compilerOptions": {
    "importsNotUsedAsValues": "error",
  }
}
```

Setting this to `error` will report an error if there is a type being imported without `import type` syntax.

```ts
import type { MyType } from './types';
export type { MyType };
```

Bundlers prefer this to help avoid potiential problems with types being incorrectly bundled.

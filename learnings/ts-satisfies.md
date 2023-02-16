# TypeScript: Satisfies operator

Typescript 4.9 introduced the new [satisfies](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-9.html#the-satisfies-operator) operator.

[Steve](https://twitter.com/Steve8708/status/1605322303319199744) explains it best using this example:

```tsx
type Route = { path: string; children?: Routes };
type Routes = Record<string, Route>;

const routes = {
  AUTH: {
    path: "/auth",
    children: {
      LOGIN: {
        path: "/login",
      },
    },
  },
  HOME: {
    path: "/",
  },
} satisfies Routes;

routes.AUTH.path; // works
routes.AUTH.children.LOGIN.path; // works
routes.HOME.children.LOGIN.path; // error
//          ^? Property 'children' does not exist on type '{ path: string; }'.
```

[Matt Pocock](https://twitter.com/mattpocockuk) has a great example of a use-case in his [TypeScript 4.9 deep dive](https://www.youtube.com/watch?v=Danki1DyiuI&t=439s) video.

# Type declarations for a Vite app

Vite uses esbuild to transpile Typescript into Javascript and [esbuild does not do any type checking](https://esbuild.github.io/content-types/#typescript).

To generate type declarations, you can use `tsc`:

```bash
tsc --declaration --emitDeclarationOnly
```

If you are building an application and want to check types only:

```bash
tsc --noEmit
```

Example `package.json`:

```json
{
  "name": "vite-app",
  "version": "0.0.0",
  "scripts": {
    "build:types": "tsc --declaration --emitDeclarationOnly"
    "check-types": "tsc --noEmit"
  },
  "devDependencies": {
    "vite": "^2.7.2",
    "typescript": "^4.0.3"
  }
}
```

It's nice to seperate the type checking from the build because:
- Vite (esbuild) builds faster without it (by 20-30x).
- It allows you to only generate type declarations when you need to (eg, preparing to package your app).

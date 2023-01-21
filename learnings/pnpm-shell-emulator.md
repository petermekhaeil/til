# Use pnpm's shell-emulator to execute scripts on all platforms

[pnpm](https://pnpm.io/) can do cross-platform scripting when [shell-emulator](https://pnpm.io/cli/run#shell-emulator) is enabled.

```bash
# .npmrc
shell-emulator=true
```

It means scripts like this will work across all platforms:

```js
"scripts": {
  "serve": "NODE_ENV=production node server"
}
```

It is powered by [@yarnpkg/shell](https://github.com/yarnpkg/berry/tree/master/packages/yarnpkg-shell) and it replaces the need to use libraries like `cross-env`.

## Learn More
- [shell-emulator](https://pnpm.io/cli/run#shell-emulator)
- [pnpm/pnpm#2881](https://github.com/pnpm/pnpm/pull/2881)
- [@pnpm/npm-lifecycle](https://github.com/pnpm/npm-lifecycle/commit/4b1a3db1f36a44a49fe7e2dd52c0099124ebdba4)

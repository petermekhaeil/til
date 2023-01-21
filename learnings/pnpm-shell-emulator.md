# Use pnpm's shell-emulator to execute scripts on all platforms

When [`shell-emulator`](https://pnpm.io/cli/run#shell-emulator) is enabled, pnpm can use a JavaScript implementation of a bash-like shell to execute scripts. It is powered by [@yarnpkg/shell](https://github.com/yarnpkg/berry/tree/master/packages/yarnpkg-shell).

```bash
# .npmrc
shell-emulator=true
```

It means scripts like this will work across all platforms:

```js
"scripts": {
  "serve": "NODE_ENV=production node server",
}
```

It replaces the need to use libraries like `cross-env`.

## Learn More
- [pnpm/pnpm#2881](https://github.com/pnpm/pnpm/pull/2881)
- [@pnpm/npm-lifecycle](https://github.com/pnpm/npm-lifecycle/commit/4b1a3db1f36a44a49fe7e2dd52c0099124ebdba4)

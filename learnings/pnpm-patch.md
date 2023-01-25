# Make changes to a dependency using pnpm patch

[pnpm patch](https://pnpm.io/cli/patch) allows you to make changes to a dependency package without having to wait for the package maintainers to release the changes.

It first extracts the package into a temporarily directory and asks you to make the changes.

```bash
$ pnpm patch my-pkg@1.0.0
You can now edit the following folder: /tmp/5ea276f0eeb3585ea64ddf4b3b7ef377
```

Once you've made the changes, you patch up the changes using [pnpm patch-commit](https://pnpm.io/cli/patch-commit):

```bash
$ pnpm patch-commit /tmp/5ea276f0eeb3585ea64ddf4b3b7ef377
```

This will create a patchfile in your project and pnpm will use this each time you do an `pnpm install`.

pnpm will reference patches in package.json:

```json
"pnpm": {
  "patchedDependencies": {
    "my-pkg@1.0.0": "patches/my-pkg@1.0.0.patch"
  }
}
```

 # npm using latest version of package
 
 If you want to use the latest version of a package when using `npm create`, you need to specify `latest` as the package version.
  
 It's why most tools will have instructions like below. It's to force npm to install the latest version of the package:
 
 ```bash
$ npx create-remix@latest
$ npm create svelte@latest
$ npx create-next-app@latest
```

The above will fetch the latest versions from the registry and execute the script.

If you do not specify a version and have previously installed the package, npm will use that previously installed version.

The same goes with the other npm commands like `npm init`, `npm exec`, `npx`.

# SvelteKit Sync

`svelte-kit sync` creates the tsconfig.json and all generated types for your project. This is useful because Sveltekit has [generated types](https://kit.svelte.dev/docs/types#generated-types).

Example:

```tsx
import { API_KEY } from '$env/static/private';
// ^? Module '"$env/static/private"' has no exported member 'API_KEY'.
```

Running `svelte-kit sync` will generate the correct types and remove the error:

```tsx
import { API_KEY } from '$env/static/private';
// ^? (alias) const API_KEY: string
```

You'll find the generated types under the `.svelte-kit` folder. Here is the one for environment variables:

```tsx
// .svelte-kit/ambient.d.ts
declare module '$env/static/private' {
	export const API_KEY: string;
  ...
}
```

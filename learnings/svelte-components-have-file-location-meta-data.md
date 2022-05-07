# Svelte components have file location meta data

Svelte nodes have a `__svelte_meta` object in development mode that contains the file location of the component that rendered that node. 

```json
{
	"loc": {
		"file": "src/routes/index.svelte",
		"line": 18,
		"column": 4,
		"char": 358
	}
}
```

You an try it out on [StackBlitz](https://node.new/sveltekit). Inspect an element using the Chrome Dev Tools and use the console:

```js
$0.__svelte_meta
```

<img width="1095" alt="Screenshot 2022-05-07 at 9 25 47 AM" src="https://user-images.githubusercontent.com/4616064/167232485-a712022b-b799-441a-a052-70f2a5ff9633.png">


(`$0` [references the last selected DOM element](https://developer.chrome.com/docs/devtools/console/utilities/#recent-many). It is part of the DevTool's Console API)

Learn more about `__svelte_meta`:

- https://github.com/sveltejs/svelte/pull/1501
- https://github.com/sveltejs/svelte/issues/1499

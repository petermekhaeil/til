# Add color using FORCE_COLOR

Node.js supports the `FORCE_COLOR` environment variable to force color in the terminal output.

```js
FORCE_COLOR=0 // 2 colors (no color)
FORCE_COLOR=1 // 16 colors
FORCE_COLOR=2 // 256 colors
FORCE_COLOR=3 // 16,777,216 colors
```

Color is automatically disabled when a process is piping output into another process. Use `FORCE_COLOR` to force color in the piped output.

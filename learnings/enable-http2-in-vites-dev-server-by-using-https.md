# Enable HTTP/2 in Vite's Dev Server by using HTTPS

Take advantage of [HTTP/2](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_2) in Vite Dev Server by enabling `server.https` in your `vite.config.js`:

```js
{
  server: {
    https: true
  }
}
```

Browsers limit the number of active connections per domain when using HTTP/1.1 and this can be avoided by enabling HTTP/2 which supports unlimited concurrent requests.

Vite's Dev server takes advantage of modern browser's support for [ES Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) and instead of bundling your site, the dev server will serve the modules via network requests in your browser. Enabling HTTP/2 can come handy in large applications that need to serve a lot of these modules.

# Override web content and HTTP response headers locally

Chrome DevTools allows you to override API responses and HTTP headers directly in the browser - this is a great feature for testing, debugging, and prototyping without modifying the backend.

You can:

- **Mock API responses**: Replace live API data with custom JSON or other content.
- **Modify HTTP headers**: Adjust headers like CORS, Content-Type, or authentication tokens to mimic different scenarios.
  
You just need to enable "Local Overrides" in DevTools and edit the response or headers for the network requests you want to tweak.

More details here: [Chrome DevTools Overrides](https://developer.chrome.com/docs/devtools/overrides)

# Send analytics data using the Beacon API

The `navigator.sendBeacon()` method is intended to be used for sending analytics data to a server.

```js
navigator.sendBeacon("/log", analyticsData);
```

- It sends the HTTP POST request asynchronously, with no access to the server response.
- The request is non-blocking, causing no delay to unload or the next navigation.

See [documentation](https://developer.mozilla.org/en-US/docs/Web/API/Beacon_API) on usage.

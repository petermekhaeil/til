# setTimeout(): Node.js vs Web

- In Node.js, [setTimeout()](https://nodejs.org/dist/latest-v18.x/docs/api/timers.html#settimeoutcallback-delay-args) returns a [\<Timeout\>](https://nodejs.org/dist/latest-v18.x/docs/api/timers.html#class-timeout) object.
- In web, [setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout) returns a number (`timeoutID`).

Both return values are passed to `clearTimeout()` to cancel the timeout.

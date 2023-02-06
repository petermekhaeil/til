# Using Promise.race() to implement request timeout

[Promise.race()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race) takes a list of promises and returns the first promise that settles (regardless if fulfilled or rejected).

Good use to implement a request timeout. It resolves the first promise that settles which will either be the fetch request or the timeout promise.

```tsx
const fetchApi = async () => {
  const res = await fetch("/api");
  return await res.json();
};

const requestTimeout = (delay: number) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => reject(new Error("Timeout")), delay);
  });
};

const data = Promise.race([fetchApi, requestTimeout(5000)]);
```

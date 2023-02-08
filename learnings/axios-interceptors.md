# Add custom config to Axios requests

[Axios](https://axios-http.com/) supports adding custom config to requests that can be used later throughout the request.

Here is an example adding a custom config called `endpointName`:

```tsx
const instance = axios.create();

const { data } = await instance.get("/api", { endpointName: "myApi" });
```

It can be used in [interceptors](https://axios-http.com/docs/interceptors):

```tsx
instance.interceptors.request.use(function (config) {
  console.log(config.endpointName);
  return config;
});

instance.interceptors.response.use(function (response) {
  console.log(response.config.endpointName);
  return response;
});
```

It is also included in Axios errors:

```tsx
instance.interceptors.response.use(null, function (error) {
  if (isAxiosError(error)) {
    console.log(error.config.endpointName);
  }

  return Promise.reject(error);
});

```

## TypeScript support

Create an `axios.d.ts` and add the custom config under `AxiosRequestConfig`:

```tsx
import "axios";

declare module "axios" {
  export interface AxiosRequestConfig {
    endpointName?: string;
  }
}
```

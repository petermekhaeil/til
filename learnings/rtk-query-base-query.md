# Implementing a custom RTK Query baseQuery

In RTK Query, services are created like this example:

```tsx
export const myApi = createApi({
  reducerPath: 'myApi',
  baseQuery: fetchBaseQuery({ baseUrl: '/api' }),
  endpoints: (builder) => ({
    getUserById: builder.query({
      query: (id) => `user/${id}`,
    }),
  }),
})
```

The `baseQuery` can be a custom utility that can wrap the default `fetchBaseQuery`. 

Below is use-case that provides meta along with each request:

```tsx
const myBaseQuery = async (args, api, extraOptions) => {
  const requestId = uuid();

  const baseResult = await fetchBaseQuery({ baseUrl: "/api" })(
    args,
    api,
    extraOptions
  );
  
  return {
    ...baseResult,
    meta: baseResult.meta && { ...baseResult.meta, requestId },
  };
};

export const myApi = createApi({
  reducerPath: "myApi",
  baseQuery: myBaseQuery,
  endpoints: (builder) => ({
    getUserById: builder.query({
      query: (id) => `user/${id}`,
    }),
  }),
});
```

`baseResult` can return an `error` if an error occured and we can use that to track which endpoint had an error. `api` parameter has an `endpoint` value that has the name of the endpoint (eg `getUserById` from the above example).


```tsx
const baseResult = await fetchBaseQuery({ baseUrl: "/api" })(
  args,
  api,
  extraOptions
);

if (baseResult.error) {
  const error = baseResult.error;
  if ("status" in error) {
    const errMsg = "error" in error ? error.error : JSON.stringify(error.data);

    console.error(`Error with ${api.endpoint}: ${error}`);
  }
}
```

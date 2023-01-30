# X-Robots-Tag

The HTTP Header `X-Robots-Tag` is used to instruct search engines on how it should handle indexing the page. It takes in any rule that can be specified in the robots `meta` tag (`<meta name="robots" content="noindex">`).

There is a whole list of values that can be used: [https://http.dev/x-robots-tag](https://http.dev/x-robots-tag).

I noticed it being used on Netlify preview URLs ([example](https://63d7d47fe551c0248a252eb7--petermekhaeil.netlify.app)):

```
X-Robots-Tag: noindex 
```

Which makes sense because these are draft URLs that should not be indexed.


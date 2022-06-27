# Proxying using Netlify Redirects

[Netlify Redirects](https://docs.netlify.com/routing/redirects/) can be used to proxy to external services.

In the below example, requests to `/api` are proxied to `https://api.domain.com`:

```bash
/api/*  https://api.example.com/:splat  200
```

Here is an example that proxies a JS script to another location:

```bash
/js/script.js https://domain.com/tracker.js 200
```

Here is an example that combines the two examples above and this one is very useful for analytics tools:

```bash
/api https://tracking-tool.com/api  200
/js/script.js https://tracking-tool.com/tracker.js 200
```

This example is useful because it can:
- Bypass CORS because the requests are from the same origin.
- Bypass blockers because the URLs don't have tracker-like keywords.

# Using Netlify Redirects to build a URL Shortener

[Netlify Redirects](https://docs.netlify.com/routing/redirects/) makes for an excellent personal URL Shortener. See [pmekh.com](https://github.com/petermekhaeil/pmekh.com) for an example.

Create a `_redirects` in a new repository and add the redirects. It supports external URLs too. Add a fallback to redirect users to another site, for example your own personal blog.

```
# _redirects

/til            https://petermekhaeil.com/today-i-learned/
/twitter        https://twitter.com/PMekhaeil
/*              https://petermekhaeil.com
```

Then create a new Netlify site and link it to your new repository. The `_redirect` is all that is required for the site to be used as a URL shortener.


Inspired by Cassidy's [cass.run](https://github.com/cassidoo/cass.run) and Kent's [netlify-shortener](https://github.com/kentcdodds/netlify-shortener). 

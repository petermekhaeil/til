# Fetch Response.statusText

Ever wondered why [Response.statusText](https://developer.mozilla.org/en-US/docs/Web/API/Response/statusText) returns an empty string? It's because it is not part of the HTTP/2 spec. 

> HTTP/2 does not define a way to carry the version or reason phrase that is included in an HTTP/1.1 status line.

Otherwise, in HTTP/1 it will return status message such as `OK`, `Continue` and `Not Found`.

Reference:

- [RFC 7540](https://tools.ietf.org/html/rfc7540#section-8.1.2.4)
- [whatwg/fetch#599](https://github.com/whatwg/fetch/issues/599)

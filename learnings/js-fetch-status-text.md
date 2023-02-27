# Fetch Response.statusText

[Response.statusText](https://developer.mozilla.org/en-US/docs/Web/API/Response/statusText) returns empty string in HTTP/2. According to spec:

> HTTP/2 does not define a way to carry the version or reason phrase that is included in an HTTP/1.1 status line.

Reference:

- [RFC 7540](https://tools.ietf.org/html/rfc7540#section-8.1.2.4)
- [whatwg/fetch#599](https://github.com/whatwg/fetch/issues/599)

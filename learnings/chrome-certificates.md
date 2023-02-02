# No browser cache with self-signed certificates

If there is a certificate error, Chromium based browsers will not cache responses and will treat a self-signed certificate as a certificate error.

See [https://bugs.chromium.org/p/chromium/issues/detail?id=110649#c8](https://bugs.chromium.org/p/chromium/issues/detail?id=110649#c8).

[Mkcert](https://github.com/FiloSottile/mkcert) can create a locally-trusted development certificate for your dev servers to prevent this from happening.

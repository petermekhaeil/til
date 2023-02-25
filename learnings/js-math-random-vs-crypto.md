# Math.random() vs Crypto.getRandomValue()

- [Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) **does not provide cryptographically secure random numbers**.
- [Crypto.getRandomValues()](https://developer.mozilla.org/en-US/docs/Web/API/Crypto/getRandomValues) returns **cryptographically strong** random values.

`Math.random()` is implemented using a [pseudo-random number generator (PRNG)](https://en.wikipedia.org/wiki/Pseudorandom_number_generator) - the random number is derived from an internal state, which is altered by a fixed algorithm for every new random number. The sequence of random numbers is deterministic. 

`Crypto.getRandomValues()` use a pseudo-random number generator seeded with a value with enough entropy. Implementations do not use a truly random number generator to guarantee enough performance but the output is suitable for cryptographic purposes.

```js
crypto.getRandomValues(new Uint8Array(10))
// Uint8Array(10) [85, 215, 117, 156, 114, 11, 222, 34, 65, 119]
```


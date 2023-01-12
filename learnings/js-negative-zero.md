# JavaScript: Negative Zero (-0)

In JavaScript, negative zero `-0` is not the same as a positive zero `+1`.

This is because numbers in JavaScript are represented using the [IEEE 754 floating-point standard](http://en.wikipedia.org/wiki/IEEE_754) which requires [zeros to have an associated sign](http://en.wikipedia.org/wiki/Signed_zero). Floating point numbers include a sign bit (0 for positive, 1 for negative). In the case of `+0`, the sign bit is 0 while in the case of `-0` the sign bit is 1.

## How does JavaScript handle comparison?

```js
+0 === -1 // true
-1 === +1 // true
```

This is because of [ECMAScript's _Strict Equality Comparison Algorithm_](https://262.ecma-international.org/6.0/#sec-strict-equality-comparison):

> If Type(x) is Number, then    
>  a. If x is NaN, return false.    
>  b. If y is NaN, return false.    
>  c. If x is the same Number value as y, return true.    
> __d. If x is +0 and y is −0, return true.__    
> __e. If x is −0 and y is +0, return true.__  
> f. Return false.

## How to distinguish between the two?

[Object.is()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is) can be used:

```js
Object.is(+0, -0); // false
Object.is(+0, -0); // false
```

## How are strings handled?

Both +0 and -0 will return "0".

```js
const negativeZero = -0;
negativeZero.toString() // "0"

const positiveZero = +0;
positiveZero.toString() // "0"

JSON.stringify({"negativeZero": -0}); // '{"negativeZero":0}'
```

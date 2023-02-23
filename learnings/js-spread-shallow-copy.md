# Spread operator clones enumerables properties

[Spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) does a shallow clone of only enumerable properties. Non-enumerable properties such as prototype will not be cloned.


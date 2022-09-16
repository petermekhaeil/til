# Array.prototype.reduce() can be typed in TypeScript

The return and initial value of the `reduce()` method can be typed using a generic.

In the example below, the array of products is converted to an object keyed by `productId`. This was safely typed with `ProductsById` being passed as a generic.

```ts
const products = [
  {
    productId: '12345',
    name: 'Product A'
  },
  {
    productId: '67890',
    name: 'Product B'
  }
];

type Product = { productId: string; name: string };
type ProductsById = Record<string, Product>;

// Transforms the array `products` into an object keyed by `productId`
const productsById = products.reduce<ProductsById>(
  (previousValue, currentValue) => {
    return {
      ...previousValue,
      [currentValue.productId]: currentValue
    };
  },
  {}
);

productsById;
// ^? const productsById: ProductsById
```

The result of `productsById` returns the below object which matches the `ProductsById` type:

```js
{
  "12345": {
    "productId": "12345",
    "name": "Product A"
  },
  "67890": {
    "productId": "67890",
    "name": "Product B"
  }
} 
```

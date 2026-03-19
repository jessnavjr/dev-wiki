# TypeScript: Function Types

```ts
type Formatter = (value: number) => string;

const formatPrice: Formatter = (value) => {
  return new Intl.NumberFormat("en-US", {
    style: "currency",
    currency: "USD",
  }).format(value);
};

console.log(formatPrice(25));
```

Notes:

- Function types make callback contracts explicit.
- Reuse named function types when the same callback shape appears in multiple places.

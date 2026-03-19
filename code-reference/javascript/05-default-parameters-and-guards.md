# JavaScript: Default Parameters And Guards

```js
function formatPrice(amount, currency = "USD") {
  if (typeof amount !== "number") {
    throw new TypeError("amount must be a number");
  }

  return new Intl.NumberFormat("en-US", {
    style: "currency",
    currency,
  }).format(amount);
}

console.log(formatPrice(19.99));
console.log(formatPrice(19.99, "EUR"));
```

Notes:

- Defaults keep common calls short.
- Guard clauses fail fast and keep the main path simpler.

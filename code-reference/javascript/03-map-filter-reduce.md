# JavaScript: Map Filter Reduce

```js
const orders = [
  { id: 1, total: 25, status: "paid" },
  { id: 2, total: 10, status: "draft" },
  { id: 3, total: 40, status: "paid" },
];

const paidTotals = orders
  .filter((order) => order.status === "paid")
  .map((order) => order.total);

const revenue = paidTotals.reduce((sum, total) => sum + total, 0);

console.log(paidTotals, revenue);
```

Notes:

- `filter` narrows the list.
- `map` transforms each item.
- `reduce` combines values into one result.

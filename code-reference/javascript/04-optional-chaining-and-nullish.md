# JavaScript: Optional Chaining And Nullish Coalescing

```js
const config = {
  api: {
    timeout: 5000,
  },
};

const timeout = config.api?.timeout ?? 3000;
const retryCount = config.api?.retryCount ?? 2;
const theme = config.ui?.theme ?? "light";

console.log(timeout, retryCount, theme);
```

Notes:

- Use `?.` when a nested value may be missing.
- Use `??` when you want a fallback only for `null` or `undefined`.

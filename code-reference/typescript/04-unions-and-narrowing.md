# TypeScript: Unions And Narrowing

```ts
function printValue(value: string | number) {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
    return;
  }

  console.log(value.toFixed(2));
}
```

Notes:

- Narrow unions with `typeof`, `in`, or custom type guards.
- After narrowing, TypeScript exposes the matching members safely.

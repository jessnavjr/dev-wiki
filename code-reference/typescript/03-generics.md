# TypeScript: Generics

```ts
function firstItem<T>(items: T[]): T | undefined {
  return items[0];
}

const project = firstItem([{ id: "p1", name: "Docs" }]);
const count = firstItem([1, 2, 3]);

console.log(project?.name, count);
```

Notes:

- Generics let one function work across many types safely.
- Use clear generic names like `T` for small local helpers or domain names for more complex APIs.

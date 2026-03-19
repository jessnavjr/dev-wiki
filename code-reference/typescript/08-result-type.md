# TypeScript: Result Type

```ts
type Result<T> =
  | { ok: true; value: T }
  | { ok: false; error: string };

function parsePort(value: string): Result<number> {
  const port = Number(value);

  if (!Number.isInteger(port) || port <= 0) {
    return { ok: false, error: "Invalid port" };
  }

  return { ok: true, value: port };
}
```

Notes:

- Result types make success and failure explicit without throwing everywhere.
- This is useful for validation and parsing helpers.

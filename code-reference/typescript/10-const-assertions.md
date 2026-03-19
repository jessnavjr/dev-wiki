# TypeScript: Const Assertions

```ts
const statuses = ["draft", "review", "published"] as const;

type Status = (typeof statuses)[number];

const config = {
  apiBaseUrl: "/api",
  retryCount: 3,
} as const;

function setStatus(status: Status) {
  console.log(status);
}

setStatus("draft");
```

Notes:

- `as const` preserves literal values instead of widening them.
- This is useful for enums-like data without creating an actual enum.

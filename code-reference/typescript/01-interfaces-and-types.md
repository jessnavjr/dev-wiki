# TypeScript: Interfaces And Types

```ts
interface User {
  id: string;
  name: string;
  active: boolean;
}

type UserSummary = {
  id: string;
  label: string;
};

const user: User = {
  id: "u1",
  name: "Avery",
  active: true,
};
```

Notes:

- Use interfaces for object contracts that may grow over time.
- Use type aliases for unions, mapped types, or compact data shapes.

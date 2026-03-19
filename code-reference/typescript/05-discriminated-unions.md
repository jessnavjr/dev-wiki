# TypeScript: Discriminated Unions

```ts
type LoadingState =
  | { status: "idle" }
  | { status: "loading" }
  | { status: "success"; data: string[] }
  | { status: "error"; message: string };

function renderState(state: LoadingState) {
  switch (state.status) {
    case "idle":
      return "Nothing loaded yet";
    case "loading":
      return "Loading...";
    case "success":
      return `Loaded ${state.data.length} items`;
    case "error":
      return state.message;
  }
}
```

Notes:

- A discriminant like `status` makes state machines much easier to model.
- This pattern is useful for API state, reducers, and UI status flows.

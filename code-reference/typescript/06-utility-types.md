# TypeScript: Utility Types

```ts
interface User {
  id: string;
  name: string;
  email: string;
  active: boolean;
}

type UserPatch = Partial<User>;
type PublicUser = Pick<User, "id" | "name">;
type RequiredUser = Required<User>;

const patch: UserPatch = { active: false };
const publicUser: PublicUser = { id: "u1", name: "Avery" };
```

Notes:

- `Partial`, `Pick`, `Omit`, and `Required` cover many common transformation cases.
- Prefer utility types over repeating similar interfaces by hand.

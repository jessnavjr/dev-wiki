# JavaScript: Destructuring And Spread

```js
const user = {
  id: 42,
  profile: { name: "Avery", role: "admin" },
  active: true,
};

const {
  id,
  profile: { name, role },
} = user;

const updatedUser = {
  ...user,
  profile: {
    ...user.profile,
    role: "editor",
  },
};

console.log(id, name, role, updatedUser.profile.role);
```

Notes:

- Destructure to pull values out cleanly.
- Spread is useful for non-mutating updates to objects and arrays.

# JavaScript: Async Await

```js
async function loadUser(userId) {
  const response = await fetch(`/api/users/${userId}`);

  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }

  return response.json();
}

async function showUser(userId) {
  try {
    const user = await loadUser(userId);
    console.log(user.name);
  } catch (error) {
    console.error("Unable to load user", error);
  }
}
```

Notes:

- Use `try` and `catch` around awaited work when failures are expected.
- Check `response.ok` for `fetch`; failed HTTP status codes do not throw automatically.

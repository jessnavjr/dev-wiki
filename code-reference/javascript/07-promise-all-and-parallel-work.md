# JavaScript: Promise All And Parallel Work

```js
async function loadDashboard() {
  const [userResponse, projectsResponse, alertsResponse] = await Promise.all([
    fetch("/api/user"),
    fetch("/api/projects"),
    fetch("/api/alerts"),
  ]);

  const [user, projects, alerts] = await Promise.all([
    userResponse.json(),
    projectsResponse.json(),
    alertsResponse.json(),
  ]);

  return { user, projects, alerts };
}
```

Notes:

- Use `Promise.all` when work can happen in parallel.
- One rejection fails the whole group, which is often what you want for dependent UI loads.

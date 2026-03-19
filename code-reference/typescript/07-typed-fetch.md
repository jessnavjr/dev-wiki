# TypeScript: Typed Fetch

```ts
interface Project {
  id: string;
  name: string;
}

async function getJson<T>(url: string): Promise<T> {
  const response = await fetch(url);

  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }

  return response.json() as Promise<T>;
}

const projects = await getJson<Project[]>("/api/projects");
console.log(projects[0]?.name);
```

Notes:

- Keep the generic at the boundary where data enters the app.
- This gives callers explicit control over the expected response shape.

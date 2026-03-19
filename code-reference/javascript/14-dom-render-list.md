# JavaScript: DOM Render List

```js
function renderProjects(container, projects) {
  container.innerHTML = "";

  for (const project of projects) {
    const item = document.createElement("li");
    item.textContent = `${project.name} (${project.status})`;
    container.appendChild(item);
  }
}

const list = document.querySelector("[data-project-list]");
renderProjects(list, [
  { name: "Docs", status: "active" },
  { name: "Portal", status: "planned" },
]);
```

Notes:

- Keep rendering logic in a single function.
- Clear old content before re-rendering when replacing the whole list.

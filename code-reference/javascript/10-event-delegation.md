# JavaScript: Event Delegation

```js
const list = document.querySelector("[data-todo-list]");

list.addEventListener("click", (event) => {
  const removeButton = event.target.closest("[data-remove-item]");

  if (!removeButton) {
    return;
  }

  const item = removeButton.closest("[data-todo-item]");
  item?.remove();
});
```

Notes:

- Event delegation works well for dynamic lists.
- Attach one listener to a stable parent instead of many listeners to children.

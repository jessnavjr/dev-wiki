# JavaScript: Form Handling

```js
const form = document.querySelector("[data-profile-form]");

form.addEventListener("submit", async (event) => {
  event.preventDefault();

  const formData = new FormData(form);
  const values = Object.fromEntries(formData.entries());

  console.log("Submitting", values);

  await fetch("/api/profile", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(values),
  });
});
```

Notes:

- `FormData` is a clean way to gather form values.
- `preventDefault()` keeps the page from reloading on submit.

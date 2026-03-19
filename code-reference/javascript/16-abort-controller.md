# JavaScript: Abort Controller

```js
const controller = new AbortController();

fetch("/api/search?q=docs", { signal: controller.signal })
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => {
    if (error.name === "AbortError") {
      console.log("Request was canceled");
      return;
    }

    console.error(error);
  });

controller.abort();
```

Notes:

- Use this to cancel outdated requests, especially in live search UIs.
- Handle `AbortError` separately from real failures.

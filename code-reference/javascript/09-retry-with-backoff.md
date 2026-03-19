# JavaScript: Retry With Backoff

```js
async function retry(task, retries = 3, delayMs = 500) {
  try {
    return await task();
  } catch (error) {
    if (retries === 0) {
      throw error;
    }

    await new Promise((resolve) => setTimeout(resolve, delayMs));
    return retry(task, retries - 1, delayMs * 2);
  }
}

retry(() => fetch("/api/health"))
  .then((response) => console.log(response.status))
  .catch((error) => console.error("Service unavailable", error));
```

Notes:

- Useful for flaky network calls and temporary service failures.
- Keep retries limited so failures still surface.

# JavaScript: Throttle

```js
function throttle(fn, wait) {
  let lastRun = 0;

  return function throttled(...args) {
    const now = Date.now();

    if (now - lastRun < wait) {
      return;
    }

    lastRun = now;
    fn.apply(this, args);
  };
}

window.addEventListener(
  "scroll",
  throttle(() => {
    console.log("Handling scroll...");
  }, 200)
);
```

Notes:

- Throttle is useful for scroll and resize handlers.
- It guarantees a maximum execution rate over time.

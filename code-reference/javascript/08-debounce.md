# JavaScript: Debounce

```js
function debounce(fn, wait) {
  let timeoutId;

  return function debounced(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => {
      fn.apply(this, args);
    }, wait);
  };
}

const saveDraft = debounce(() => {
  console.log("Saving draft...");
}, 300);
```

Notes:

- Use debounce for search inputs, resize handlers, and autosave.
- It reduces repeated calls during bursts of user activity.

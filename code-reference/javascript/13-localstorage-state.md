# JavaScript: Local Storage State

```js
const storageKey = "ui-preferences";

function loadPreferences() {
  const raw = localStorage.getItem(storageKey);
  return raw ? JSON.parse(raw) : { theme: "light", compact: false };
}

function savePreferences(preferences) {
  localStorage.setItem(storageKey, JSON.stringify(preferences));
}

const preferences = loadPreferences();
savePreferences({ ...preferences, compact: true });
```

Notes:

- Store only small UI state in `localStorage`.
- Always serialize objects with `JSON.stringify`.

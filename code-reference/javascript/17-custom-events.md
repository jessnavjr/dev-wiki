# JavaScript: Custom Events

```js
const panel = document.querySelector("[data-panel]");

panel.addEventListener("panel:open", (event) => {
  console.log("Opened panel", event.detail.id);
});

panel.dispatchEvent(
  new CustomEvent("panel:open", {
    detail: { id: "settings" },
    bubbles: true,
  })
);
```

Notes:

- Custom events are useful for decoupled UI communication.
- Pass structured data through `detail`.

# JavaScript: Copy To Clipboard

```js
async function copyText(text) {
  try {
    await navigator.clipboard.writeText(text);
    console.log("Copied to clipboard");
  } catch (error) {
    console.error("Copy failed", error);
  }
}

copyText("https://example.com/docs");
```

Notes:

- Useful for share links, tokens, and generated commands.
- Clipboard APIs usually require a secure context and user interaction.

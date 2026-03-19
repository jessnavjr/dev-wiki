# JavaScript: Import Export Modules

```js
// math.js
export function sum(a, b) {
  return a + b;
}

export const version = "1.0.0";

// app.js
import { sum, version } from "./math.js";

console.log(sum(2, 3));
console.log(version);
```

Notes:

- Prefer named exports for shared utilities.
- Keep imports explicit so dependencies stay obvious.

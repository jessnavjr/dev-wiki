# TypeScript: Classes And Implements

```ts
interface Logger {
  log(message: string): void;
}

class ConsoleLogger implements Logger {
  log(message: string) {
    console.log(`[log] ${message}`);
  }
}

const logger: Logger = new ConsoleLogger();
logger.log("Ready");
```

Notes:

- `implements` makes class contracts explicit.
- TypeScript checks that the class satisfies the interface shape.

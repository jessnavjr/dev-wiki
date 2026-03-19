# Azure DevOps Wiki Variation: Sequence API Call

```md
::: mermaid
sequenceDiagram
    participant User
    participant WebApp
    participant API
    participant DB
    User->>WebApp: Submit form
    WebApp->>API: POST /orders
    API->>DB: Insert order
    DB-->>API: Order id
    API-->>WebApp: 201 Created
    WebApp-->>User: Show confirmation
:::
```

Notes:

- Good fit for service call paths and incident explanations.

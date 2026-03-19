# Azure DevOps Wiki Variation: ER Data Model

```md
::: mermaid
erDiagram
    PROJECT ||--o{ TASK : contains
    USER ||--o{ TASK : assigned_to

    PROJECT {
        string project_id
        string name
    }
    TASK {
        string task_id
        string status
    }
:::
```

Notes:

- Good for lightweight schema pages in internal docs.

# Mermaid: State Lifecycle

````md
```mermaid
stateDiagram-v2
    [*] --> Draft
    Draft --> Review
    Review --> Approved
    Review --> Rejected
    Rejected --> Draft
    Approved --> Published
    Published --> Archived
```
````

Notes:

- Use for workflow status, ticket lifecycles, and release states.

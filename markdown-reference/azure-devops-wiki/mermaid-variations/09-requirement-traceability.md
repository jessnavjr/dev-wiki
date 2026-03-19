# Azure DevOps Wiki Variation: Requirement Traceability

## Diagram

```mermaid
requirementDiagram
    requirement auth_req {
        id: REQ-101
        text: login requires MFA
        risk: high
        verifymethod: test
    }
    element login_service {
        type: service
    }
    login_service - satisfies -> auth_req
```

## Syntax

```md
::: mermaid
requirementDiagram
    requirement auth_req {
        id: REQ-101
        text: login requires MFA
        risk: high
        verifymethod: test
    }
    element login_service {
        type: service
    }
    login_service - satisfies -> auth_req
:::
```

Notes:

- Useful when wiki pages act as internal requirement records.

# Mermaid: Requirement Traceability

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

    test_case mfa_test {
        id: TEST-88
        desc: MFA challenge succeeds
    }

    login_service - satisfies -> auth_req
    mfa_test - verifies -> auth_req
```

## Syntax

````md
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

    test_case mfa_test {
        id: TEST-88
        desc: MFA challenge succeeds
    }

    login_service - satisfies -> auth_req
    mfa_test - verifies -> auth_req
```
````

Notes:

- Use for compliance, validation, and verification mappings.

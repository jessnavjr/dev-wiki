# Mermaid: C4 Diagrams

````md
```mermaid
C4Context
    title System context
    Person(user, "End User", "Uses the product")
    System(app, "Docs Portal", "Hosts docs and diagrams")
    System_Ext(idp, "Identity Provider", "Handles sign-in")
    Rel(user, app, "Reads docs")
    Rel(app, idp, "Authenticates with")

%% Mermaid also supports these C4 variants:
%% C4Container
%% C4Component
%% C4Dynamic
%% C4Deployment
```
````

Notes:

- Use `C4Context` for system context, `C4Container` for deployable parts, `C4Component` for internals, `C4Dynamic` for interactions, and `C4Deployment` for runtime topology.
- C4 support is experimental and depends on Mermaid renderer version.

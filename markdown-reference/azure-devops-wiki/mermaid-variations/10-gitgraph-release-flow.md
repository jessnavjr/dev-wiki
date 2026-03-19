# Azure DevOps Wiki Variation: GitGraph Release Flow

```md
::: mermaid
gitGraph
    commit id: "Initial"
    branch develop
    checkout develop
    commit id: "Feature A"
    checkout main
    merge develop id: "Release merge"
:::
```

Notes:

- Useful for branch policy and release workflow pages.

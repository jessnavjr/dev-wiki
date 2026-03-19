# Azure DevOps Wiki Variation: Links Images And Work Items

## Example

[Sibling page](./another-page.md)

[Wiki page](/parent-page/child-page)

[Section on another page](/parent-page/child-page#deployment-notes)

See work item #1234.

Use \#ff0000 if you need a literal hash value.

## Syntax

```md
[Sibling page](./another-page.md)
[Wiki page](/parent-page/child-page)
[Section on another page](/parent-page/child-page#deployment-notes)

See work item #1234.

![Architecture diagram](./images/architecture.png)
![Scaled image](./images/architecture.png =500x250)

Use \#ff0000 if you need a literal hash value.
```

Notes:

- `#1234` can resolve as a work item reference.
- Wiki images support size syntax like `=500x250`.

# Azure DevOps Wiki Variation: TOC Subpages And Sections

## Example

The `[[_TOC_]]` and `[[_TOSP_]]` tokens are Azure DevOps wiki features and do not render in a standard browser Markdown view.

<details>
  <summary>Expand deployment checklist</summary>

  <h2>Deployment</h2>
  <ul>
    <li><input type="checkbox" disabled> Confirm approvals</li>
    <li><input type="checkbox" disabled> Run smoke tests</li>
  </ul>
</details>

## Syntax

```md
[[_TOC_]]

[[_TOSP_]]

<details>
  <summary>Expand deployment checklist</summary>

  ## Deployment
  - [ ] Confirm approvals
  - [ ] Run smoke tests
</details>
```

Notes:

- `[[_TOC_]]` and `[[_TOSP_]]` are case-sensitive.
- Leave a blank line after `</summary>` for the collapsible section to render correctly.

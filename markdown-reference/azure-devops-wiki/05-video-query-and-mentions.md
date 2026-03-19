# Azure DevOps Wiki Variation: Video Query And Mentions

## Example

Azure DevOps-specific `::: video`, `query-table`, and `@mentions` do not render as full features in a normal browser Markdown view.

[Open embedded video target](https://www.youtube.com/watch?v=OtqFyBA6Dbk)

Query table example: `query-table 6ff7777e-8ca5-4f04-a7f6-9e63737dddf7`

@team-alias please review this update.

## Syntax

````md
::: video
<iframe width="640" height="360" src="https://www.youtube.com/embed/OtqFyBA6Dbk" allowfullscreen style="border:none"></iframe>
:::

:::
query-table 6ff7777e-8ca5-4f04-a7f6-9e63737dddf7
:::

@team-alias please review this update.
````

Notes:

- `query-table` embeds Azure Boards query results by GUID.
- `@alias` mentions notify people or groups in supported wiki contexts.
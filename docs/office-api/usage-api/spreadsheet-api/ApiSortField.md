# ApiSortField

Class representing a single sort field within a SortFields collection.

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Key | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns or sets the sort key range (the full table column). |
| Order | [SortOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortOrder.md) | Returns or sets the sort order. |
| Parent | [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) | Returns the parent SortFields collection. |
| Priority | number | Returns or sets the 1-based sort priority. |
| SortOn | [XlSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortOn.md) | Returns or sets what value is used as the sort criteria. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/Delete.md) | None | Removes this sort field from the collection. |
| [GetKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetKey.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the sort key range (the full table column). |
| [GetOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetOrder.md) | [SortOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortOrder.md) | Returns the sort order: "xlAscending" or "xlDescending". |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetParent.md) | [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) | Returns the parent SortFields collection. |
| [GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetPriority.md) | number | Returns the 1-based priority of this sort field within the collection. |
| [GetSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetSortOn.md) | [XlSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortOn.md) | Returns the sort-on type: "xlSortOnValues", "xlSortOnCellColor", "xlSortOnFontColor", "xlSortOnIcon". |
| [GetSortOnValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/GetSortOnValue.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| null | Returns the value (color or null) by which this sort field is sorted. |
| [ModifyKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/ModifyKey.md) | None | Changes the sort key column. |
| [SetOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetOrder.md) | None | Sets the sort order. |
| [SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetPriority.md) | None | Sets the 1-based priority of this sort field, repositioning it within the collection. |
| [SetSortOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetSortOn.md) | None | Sets the sort-on type. |
| [SetSortOnColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortField/Methods/SetSortOnColor.md) | None | Sets the color for color-based sorting. |

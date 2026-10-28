# ApiSort

Class representing the sort state of a list object (table).

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Header | string | Returns the header setting (always "xlYes" for a ListObject). |
| MatchCase | boolean | Returns or sets whether the sort is case-sensitive. |
| Orientation | [XlSortOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortOrientation.md) | Returns or sets the sort orientation. |
| Parent | [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) | Returns the parent list object. |
| Rng | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the data body range that the sort applies to. |
| SortFields | [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) | Returns the collection of sort fields. |
| SortMethod | [XlSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortMethod.md) | Returns or sets the sort method for Chinese text. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Apply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/Apply.md) | None | Applies the current sort settings to the table. |
| [GetHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetHeader.md) | string | Returns the header setting. |
| [GetMatchCase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetMatchCase.md) | boolean | Returns whether the sort is case-sensitive. |
| [GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetOrientation.md) | [XlSortOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortOrientation.md) | Returns the sort orientation: "xlTopToBottom" or "xlLeftToRight". |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetParent.md) | [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) | Returns the parent list object. |
| [GetRng](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetRng.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the data body range that the sort applies to. |
| [GetSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetSortFields.md) | [ApiSortFields](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSortFields.md) | Returns the sort fields collection. |
| [GetSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/GetSortMethod.md) | [XlSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlSortMethod.md) | Returns the sort method: "xlPinYin" or "xlStroke". |
| [SetMatchCase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetMatchCase.md) | None | Sets whether the sort is case-sensitive. |
| [SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetOrientation.md) | None | Sets the sort orientation. |
| [SetSortMethod](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort/Methods/SetSortMethod.md) | None | Sets the sort method. |

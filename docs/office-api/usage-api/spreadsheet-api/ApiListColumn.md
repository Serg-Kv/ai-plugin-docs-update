# ApiListColumn

Class representing a single column in a list object (table).

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| DataBodyRange | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the data body range of the column, excluding header and totals rows. |
| Index | number | Returns the 1-based index of the column within the table. |
| Name | string | Returns or sets the name of the column. |
| Parent | [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) | Returns the parent list object. |
| Range | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the full range of the column, including header and totals rows. |
| Total | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the totals row cell range for the column. |
| TotalsCalculation | [XlTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTotalsCalculation.md) | Returns or sets the totals row calculation type. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/Delete.md) | boolean | Deletes the column from the table. |
| [GetDataBodyRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetDataBodyRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the data body of the column, excluding the header and totals rows. |
| [GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetIndex.md) | number | Returns the 1-based index of the column within the table. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetName.md) | string | Returns the name of the table column. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetParent.md) | [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) | Returns the parent list object. |
| [GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the entire column, including the header and totals rows. |
| [GetTotal](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetTotal.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the totals row cell for the column. |
| [GetTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/GetTotalsCalculation.md) | [XlTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTotalsCalculation.md) | Returns the totals calculation type for the column. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/SetName.md) | None | Sets the name of the table column. |
| [SetTotalsCalculation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn/Methods/SetTotalsCalculation.md) | None | Sets the totals calculation type for the column. |

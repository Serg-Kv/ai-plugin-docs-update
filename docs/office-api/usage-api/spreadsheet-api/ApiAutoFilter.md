# ApiAutoFilter

Class representing worksheet autofilters.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| FilterMode | boolean | Returns a value that indicates whether the worksheet has an AutoFilter applied. |
| Filters | [ApiFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter.md)[] | Returns the array of ApiFilter objects that represents the filters applied to the range. |
| Parent | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the ApiWorksheet object that contains the AutoFilter. |
| Range | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the ApiRange object that represents the AutoFilter range; null if no AutoFilter is defined. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [ApplyFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/ApplyFilter.md) | void | Reapplies the AutoFilter to the worksheet using the existing filter criteria. |
| [GetFilterMode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetFilterMode.md) | boolean | Returns a value that indicates whether the worksheet has an AutoFilter applied. |
| [GetFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetFilters.md) | [ApiFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter.md)[] | Returns the array of ApiFilter objects that represents the filters applied to the AutoFilter range. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetParent.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) \| [ApiListObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject.md) | Returns the parent object for the AutoFilter — either the ApiWorksheet the filter is applied to, or the ApiListObject if the filter belongs to a table. |
| [GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/GetRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the ApiRange object that represents the AutoFilter range. |
| [ShowAllData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter/Methods/ShowAllData.md) | void | Clears all filters and displays all rows in the AutoFilter range. |

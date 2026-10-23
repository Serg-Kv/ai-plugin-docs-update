# ApiFilter

Class representing a single AutoFilter column.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Criteria1 | string \| string[] \| number \| [XlDynamicFilterCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDynamicFilterCriteria.md) \| null | Returns the first criteria associated with the filter. |
| Criteria2 | string \| null | Returns the second criteria associated with the filter (used with xlAnd/xlOr). |
| On | boolean | Indicates whether any filter is applied to this column. |
| Operator | [XlAutoFilterOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlAutoFilterOperator.md) \| null | Returns the operator used for the filter on this column. |
| Parent | [ApiAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter.md) | Returns the parent filters collection for this filter column. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [GetCriteria1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetCriteria1.md) | string \| string[] \| number \| [XlDynamicFilterCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDynamicFilterCriteria.md) \| null | Returns the first criteria associated with the filter for this column. |
| [GetCriteria2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetCriteria2.md) | string \| null | Returns the second criteria associated with the filter for this column. |
| [GetOn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetOn.md) | boolean | Indicates whether any filter is applied on this column. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetOperator.md) | [XlAutoFilterOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlAutoFilterOperator.md) \| null | Returns the operator used for the filter on this column. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFilter/Methods/GetParent.md) | [ApiAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter.md) | Returns the parent filters collection for this filter column. |

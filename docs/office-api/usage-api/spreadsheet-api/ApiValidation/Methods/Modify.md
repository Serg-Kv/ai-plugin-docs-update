# Modify

Modifies data validation for a range.

## Syntax

```javascript
expression.Modify(Type, AlertStyle, Operator, Formula1, Formula2);
```

`expression` - A variable that represents an [ApiValidation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Type | Optional | [ValidationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationType.md) |  | The validation type. |
| AlertStyle | Optional | [ValidationAlertStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationAlertStyle.md) |  | The validation alert style. |
| Operator | Optional | [ValidationOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationOperator.md) |  | The data validation operator. |
| Formula1 | Optional | string \| number \| [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) |  | The first formula in the data validation. |
| Formula2 | Optional | string \| number \| [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) |  | The second formula in the data validation. |

## Returns

[ApiValidation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation.md) \| null

## Example

Update the restriction rule on a group of cells without removing it first in a spreadsheet.

```javascript editor-xlsx
// How do I change the data rule that controls what values are allowed in selected cells in a spreadsheet?

// Replace an existing entry limit with new conditions so the affected cells enforce different criteria in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRange("A1").SetValue("Data Validation for decimal to be more than 10 for A2 and A5");
const range = worksheet.GetRange("A2:A5");
const targetRange = worksheet.GetRange("A4:A5");
range.SetValue("10");
const validation = range.GetValidation();
validation.Add("xlValidateDecimal", "xlValidAlertWarning", "xlGreater", "12");
targetRange.GetValidation().Modify("xlValidateDecimal", "xlValidAlertStop", "xlLess", "12");
worksheet.GetRange("A6").SetValue("Data Validation is now modified for A4:A5, to accept values less than 12.");
```

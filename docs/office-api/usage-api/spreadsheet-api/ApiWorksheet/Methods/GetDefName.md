# GetDefName

Returns the ApiName object by the worksheet name.

## Syntax

```javascript
expression.GetDefName(defName);
```

`expression` - A variable that represents an [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| defName | Required | string |  | The defined name. |

## Returns

[ApiName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiName.md) \| null

## Example

Retrieve a named range from the active sheet by its name in a spreadsheet.

```javascript editor-xlsx
// How do I look up a named range on a worksheet in a spreadsheet?

// Find a specific named range and read its title in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.GetRange("A1").SetValue("1");
worksheet.GetRange("B1").SetValue("2");
worksheet.AddDefName("numbers", "Sheet1!$A$1:$B$1");
let defName = worksheet.GetDefName("numbers");
worksheet.GetRange("A3").SetValue("DefName: " + defName.GetName());
```

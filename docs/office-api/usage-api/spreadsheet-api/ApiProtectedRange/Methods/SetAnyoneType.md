# SetAnyoneType

Sets the type of the "Anyone" user to the current protected range.

## Syntax

```javascript
expression.SetAnyoneType(protectedRangeUserType);
```

`expression` - A variable that represents an [ApiProtectedRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| protectedRangeUserType | Required | [ProtectedRangeUserType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ProtectedRangeUserType.md) |  | The user type of the protected range. |

## Returns

boolean

## Example

Set the default access level that applies to all users of a protected range in a spreadsheet.

```javascript editor-xlsx
// How do I control what anyone without explicit permission can do with a locked range in a spreadsheet?

// Restrict or open a protected range to everyone by choosing a blanket access level in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.AddProtectedRange("protectedRange", "Sheet1!$A$1:$B$1");
let protectedRange = worksheet.GetProtectedRange("protectedRange");
protectedRange.SetAnyoneType("CanView");
```

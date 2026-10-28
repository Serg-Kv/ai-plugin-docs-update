# AddUser

Sets a user to the current protected range.

## Syntax

```javascript
expression.AddUser(sId, sName, protectedRangeUserType);
```

`expression` - A variable that represents an [ApiProtectedRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRange.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| sId | Required | string |  | The user ID. |
| sName | Required | string |  | The user name. |
| protectedRangeUserType | Required | [ProtectedRangeUserType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ProtectedRangeUserType.md) |  | The user type of the protected range. |

## Returns

[ApiProtectedRangeUserInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo.md) \| null

## Example

Grant a user access to a protected range in a spreadsheet.

```javascript editor-xlsx
// How do I allow a specific person to edit or view a locked range in a spreadsheet?

// Protect a cell range and then give a named user permission to work with it in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.AddProtectedRange("protectedRange", "$A$1:$B$1");
let protectedRange = worksheet.GetProtectedRange("protectedRange");
protectedRange.AddUser("userId", "name", "CanView");
```

# GetType

Returns the type property of the current user's information.

## Syntax

```javascript
expression.GetType();
```

`expression` - A variable that represents an [ApiProtectedRangeUserInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiProtectedRangeUserInfo.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ProtectedRangeUserType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ProtectedRangeUserType.md)

## Example

Read the permission type assigned to a user on a protected range in a spreadsheet.

```javascript editor-xlsx
// How do I check what access level a user has on a protected range in a spreadsheet?

// Verify whether a collaborator can view or edit a locked area in a spreadsheet.

let worksheet = Api.GetActiveSheet();
worksheet.AddProtectedRange("protectedRange", "$A$1:$B$1").AddUser("userId", "name", "CanView");
let protectedRange = worksheet.GetProtectedRange("protectedRange");
let userInfo = protectedRange.GetUser("userId");
let userType = userInfo.GetType();
worksheet.GetRange("A3").SetValue("Type: " + userType);
```

# GetByInternalId

Returns the object by it's internal ID.

## Syntax

```javascript
expression.GetByInternalId(id);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| id | Required | string |  | the object internal ID. |

## Returns

[FloatObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/FloatObject.md) \| [ApiDocumentContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocumentContent.md) \| [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph.md) \| [ApiTableRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableRow.md) \| [ApiTableCell](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell.md)

## Example

Get an object by its internal ID in a PDF.

```javascript editor-pdf
// Useful for finding a PDF API object by its internal identifier.

// Create a field, get its internal ID, and retrieve the same field by that ID.

let doc = Api.GetDocument();
let page = doc.GetPage(0);
let textField = Api.CreateTextField([10, 10, 160, 30]);
page.AddObject(textField);

let internalId = textField.GetInternalId();
let fieldById = Api.GetByInternalId(internalId);
fieldById.SetValue("Field was found by internal ID");
```

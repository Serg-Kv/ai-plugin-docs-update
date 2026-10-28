# AddCheckBoxContentControl

Adds a new checkbox content control to the document.

## Syntax

```javascript
expression.AddCheckBoxContentControl(checkBoxPr);
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| checkBoxPr | Required | [ContentControlCheckBoxPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ContentControlCheckBoxPr.md) |  | The configuration object for the checkbox. |

## Returns

[ApiInlineLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt.md)

## Example

Add a checkbox content control to a document.

```javascript editor-docx
// How do I insert a checkbox content control in a document?

// Embed a pre-checked checkbox field to capture boolean input in a document.

let doc = Api.GetDocument();
doc.AddCheckBoxContentControl({checked : true});
```

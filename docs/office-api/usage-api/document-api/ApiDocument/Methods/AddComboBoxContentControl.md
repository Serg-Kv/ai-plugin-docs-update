# AddComboBoxContentControl

Adds a new combo box content control to the document.

## Syntax

```javascript
expression.AddComboBoxContentControl(list, selected);
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| list | Optional | [ContentControlListItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ContentControlListItem.md)[] |  | An array of objects representing the items in the combo box. |
| selected | Optional | string |  | The optional value of the item that should be selected by default (must match one of the ListItem.Value). |

## Returns

[ApiInlineLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiInlineLvlSdt.md)

## Example

Add a combo box content control to a document.

```javascript editor-docx
// How do I insert a combo box content control in a document?

// Provide users with a selectable dropdown list by inserting a combo box field in a document.

let doc = Api.GetDocument();
doc.AddComboBoxContentControl();
```

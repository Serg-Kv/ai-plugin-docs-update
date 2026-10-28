# SetColor

Sets the tag color of the content control.

## Syntax

```javascript
expression.SetColor(color);
```

`expression` - A variable that represents an [ApiBlockLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null |  | The tag color. Pass *null* to remove the color. |

## Returns

boolean

## Example

Set the tag color of a content control in a document.

```javascript editor-docx
// How do I change the tag color of a content control in a document?

// Color-code a content control tag to categorize or identify it visually in a document.

let doc = Api.GetDocument();
let blockLvlSdt = Api.CreateBlockLvlSdt();
blockLvlSdt.SetColor(Api.RGB(0, 0, 255));
blockLvlSdt.GetContent().GetElement(0).AddText("This is a block text content control with a blue tag color.");
doc.AddElement(0, blockLvlSdt);
```

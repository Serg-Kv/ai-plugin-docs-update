# SetColor

Sets the text color to the current text run.

Inherited from [ApiTextPr.SetColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetColor.md).

## Syntax

```javascript
expression.SetColor(color);
```

`expression` - A variable that represents an [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) \| null |  | The text color. Pass *null* to remove the text color. |

## Returns

[ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md)

## Example

Apply a specific color to the text of a run in a document.

```javascript editor-docx
// How do I change the color of a piece of text in a document?

// Give a run a distinct hue to make it stand out visually in a document.

const doc = Api.GetDocument();
const paragraph = doc.GetElement(0);

const firstRun = Api.CreateRun();
firstRun.AddText('This is a text run with the font color set to orange.');
firstRun.SetColor(Api.HexColor('#FF6F3D'));
paragraph.AddElement(firstRun);

const secondRun = Api.CreateRun();
secondRun.AddText('The text uses a bluish color created with HexColor method.');
const hexColor = Api.HexColor('#219ebc');
secondRun.SetColor(hexColor);
paragraph.AddElement(secondRun);
```

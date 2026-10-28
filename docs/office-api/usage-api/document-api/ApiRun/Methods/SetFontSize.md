# SetFontSize

Sets the font size to the characters of the current text run.

Inherited from [ApiTextPr.SetFontSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetFontSize.md).

## Syntax

```javascript
expression.SetFontSize(size);
```

`expression` - A variable that represents an [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| size | Required | [hps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/hps.md) \| null |  | The text size value measured in half-points (1/144 of an inch). Pass *null* to remove the font size. |

## Returns

[ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md)

## Example

Change the font size of a text run in a document.

```javascript editor-docx
// How do I make the text in a run larger or smaller in a document?

// Adjust the character size of a run to control its visual weight in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
let run = Api.CreateRun();
run.AddText("This is just a sample text. ");
paragraph.AddElement(run);
run = Api.CreateRun();
run.SetFontSize(30);
run.AddText("This is a text run with the font size set to 15 points (30 half-points).");
paragraph.AddElement(run);
```

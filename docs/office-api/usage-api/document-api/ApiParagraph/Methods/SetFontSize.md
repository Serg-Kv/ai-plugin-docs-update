# SetFontSize

Sets the font size to the characters of the current paragraph.

## Syntax

```javascript
expression.SetFontSize(fontSize);
```

`expression` - A variable that represents an [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| fontSize | Required | [hps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/hps.md) \| null |  | The text size value measured in half-points (1/144 of an inch). Pass *null* to remove the font size. |

## Returns

[ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md)

## Example

Set the text size for all characters in a paragraph in a document.

```javascript editor-docx
// How do I make the text in a paragraph larger or smaller in a document?

// Resize paragraph text to stand out or fit a specific layout requirement in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is just a sample paragraph with the font size set to 24 points.");
paragraph.SetFontSize(48);
```

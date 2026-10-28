# SetBold

Sets the bold property to the text character.

Inherited from [ApiTextPr.SetBold](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetBold.md).

## Syntax

```javascript
expression.SetBold(isBold);
```

`expression` - A variable that represents an [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| isBold | Required | boolean |  | Specifies that the contents of the run are displayed bold. |

## Returns

[ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md)

## Example

Apply bold formatting to a text run in a document.

```javascript editor-docx
// How do I make a piece of text appear bold in a document?

// Emphasize a run by making its characters heavier and thicker in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
let run = Api.CreateRun();
run.AddText("This is just a sample text. ");
paragraph.AddElement(run);
run = Api.CreateRun();
run.SetBold(true);
run.AddText("This is a text run with the font set to bold.");
paragraph.AddElement(run);
```

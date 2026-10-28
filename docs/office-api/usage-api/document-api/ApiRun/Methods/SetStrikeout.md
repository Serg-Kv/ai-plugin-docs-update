# SetStrikeout

Specifies that the contents of the run are displayed with a single horizontal line through the center of the line.

Inherited from [ApiTextPr.SetStrikeout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetStrikeout.md).

## Syntax

```javascript
expression.SetStrikeout(isStrikeout);
```

`expression` - A variable that represents an [ApiRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| isStrikeout | Required | boolean |  | Specifies that the contents of the current run are displayed struck through. |

## Returns

[ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md)

## Example

Draw a horizontal line through the middle of a text run in a document.

```javascript editor-docx
// How do I cross out a word or phrase to show it has been removed in a document?

// Mark text as deleted or negated by adding a strikethrough line in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
let run = Api.CreateRun();
run.AddText("This is just a sample text. ");
paragraph.AddElement(run);
run = Api.CreateRun();
run.SetStrikeout(true);
run.AddText("This is a text run with the text struck out with a single line.");
paragraph.AddElement(run);
```

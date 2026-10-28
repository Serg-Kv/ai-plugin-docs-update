# SetSpacing

Sets the text spacing measured in twentieths of a point.

Inherited from [ApiTextPr.SetSpacing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr/Methods/SetSpacing.md).

## Syntax

```javascript
expression.SetSpacing(spacing);
```

`expression` - A variable that represents an [ApiRangeTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRangeTextPr.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| spacing | Required | [twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) \| null |  | The value of the text spacing measured in twentieths of a point (1/1440 of an inch). Pass *null* to remove the text spacing. |

## Returns

[ApiTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextPr.md)

## Example

Set the amount of space between characters in a document.

```javascript editor-docx
// How do I increase or decrease the gap between letters in a document?

// Control how tightly or loosely characters are spaced along a line in a document.

let doc = Api.GetDocument();
let textPr = doc.GetDefaultTextPr();
textPr.SetSpacing(80);
let paragraph = doc.GetElement(0);
paragraph.AddText("A sample text with the spacing set to 4 points (80 twentieths of a point).");
```

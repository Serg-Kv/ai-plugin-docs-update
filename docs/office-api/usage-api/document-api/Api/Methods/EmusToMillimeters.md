# EmusToMillimeters

Converts English Metric Units (EMUs) to millimeters.

## Syntax

```javascript
expression.EmusToMillimeters(emu);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| emu | Required | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/EMU.md) |  | The value in English Metric Units (EMUs). |

## Returns

[mm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/mm.md)

## Example

Display a measurement converted from internal units to millimeters in a document.

```javascript editor-docx
// How do I show a size value in millimeters inside a document?

// Write the millimeter equivalent of a raw numeric measurement into a paragraph in a document.

const doc = Api.GetDocument();
const paragraph = Api.CreateParagraph();

const emus = 780000;
const millimeters = Api.EmusToMillimeters(emus);
paragraph.AddText(emus + ' emus are equal to ' + millimeters + ' millimeters.');
doc.Push(paragraph);
```

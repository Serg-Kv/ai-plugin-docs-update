# MillimetersToEmus

Converts millimeters to English Metric Units (EMUs).

The result is an integer value.

## Syntax

```javascript
expression.MillimetersToEmus(mm);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| mm | Required | [mm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/mm.md) |  | The value in millimeters. |

## Returns

[EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/EMU.md)

## Example

Convert a millimeter value to English metric units and display the result in a document.

```javascript editor-docx
// How do I translate a measurement from millimeters to English metric units in a document?

// Show the equivalent English metric unit value for a given number of millimeters in a document.

const doc = Api.GetDocument();
const paragraph = Api.CreateParagraph();

const millimeters = 0.2001;
const emus = Api.MillimetersToEmus(millimeters);
paragraph.AddText(millimeters + ' millimeters are equal to ' + emus + ' emus (value is rounded to integer).');
doc.Push(paragraph);
```

# SetRotation

Sets page rotation angle

## Syntax

```javascript
expression.SetRotation(angle);
```

`expression` - A variable that represents an [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| angle | Required | [Degree](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Degree.md) |  | The rotation angle in degrees. Must be a multiple of 90. |

## Returns

boolean

## Example

Rotate a page to a specific angle in a PDF.

```javascript editor-pdf
// Useful for turning a page to face the right direction in a PDF.

// Apply a rotation transformation to change the page orientation in a PDF.

let doc = Api.GetDocument();
doc.AddPage(0);
let page = doc.GetPage(0);
page.SetRotation(90);
```

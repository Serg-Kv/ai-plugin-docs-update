# RGB

Creates an RGB color from red, green and blue components.

## Syntax

```javascript
expression.RGB(r, g, b);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| r | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/byte.md) |  | Red component (0-255). |
| g | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/byte.md) |  | Green component (0-255). |
| b | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/byte.md) |  | Blue component (0-255). |

## Returns

[ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md)

## Example

Create a color using red, green, and blue values in a PDF.

```javascript editor-pdf
// How do I define a custom color in a PDF?

// Set a shape's fill color using RGB values in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const color = Api.RGB(186, 218, 85);
const fill = Api.CreateSolidFill(color);
const stroke = Api.CreateStroke(36000, Api.CreateSolidFill(Api.RGB(0, 0, 0)));
const shape = Api.CreateShape("rect", 150 * 36000, 65 * 36000, fill, stroke);
shape.SetPosition(608400, 1267200);
page.AddObject(shape);
```

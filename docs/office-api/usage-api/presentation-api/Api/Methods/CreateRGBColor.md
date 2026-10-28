# CreateRGBColor

Creates an RGB color setting the appropriate values for the red, green and blue color components.

## Syntax

```javascript
expression.CreateRGBColor(r, g, b);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| r | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/byte.md) |  | Red color component value. |
| g | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/byte.md) |  | Green color component value. |
| b | Required | [byte](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/byte.md) |  | Blue color component value. |

## Returns

[ApiRGBColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiRGBColor.md)

## Example

Define a custom color using red, green, and blue values in a presentation.

```javascript editor-pptx
// How do I specify a color using RGB numbers in a presentation?

// Create a gradient with custom RGB color stops in a presentation.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);
slide.RemoveAllObjects();

const rgbColor = Api.CreateRGBColor(255, 111, 61);
const gs1 = Api.CreateGradientStop(Api.CreatePresetColor("peachPuff"), 0);
const gs2 = Api.CreateGradientStop(rgbColor, 100000);
const fill = Api.CreateRadialGradientFill([gs1, gs2]);
const stroke = Api.CreateStroke(0, Api.CreateNoFill());
const drawing = Api.CreateShape("flowChartMagneticTape", 300 * 36000, 130 * 36000, fill, stroke);
drawing.SetPosition(608400, 1267200);
slide.AddObject(drawing);
```

# SetFill

Sets the fill formatting properties to the current graphic object.

Inherited from [ApiDrawing.SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiDrawing/Methods/SetFill.md).

## Syntax

```javascript
expression.SetFill(oFill);
```

`expression` - A variable that represents an [ApiImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiImage.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| oFill | Required | [ApiFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiFill.md) |  | The fill type used to fill the graphic object. |

## Returns

boolean

## Example

Set a solid fill on a drawing object through the base ApiDrawing interface in a presentation.

```javascript editor-pptx
// The SetFill method works for any graphic object on a slide, including images and groups, not only shapes.

// Add a rectangle to a slide and fill it with a solid blue-grey color.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);
const stroke = Api.CreateStroke(0, Api.CreateNoFill());
const drawing = Api.CreateShape("rect", 150 * 36000, 80 * 36000, Api.CreateNoFill(), stroke);
drawing.SetPosition(608400, 1267200);
slide.AddObject(drawing);
const fill = Api.CreateSolidFill(Api.RGB(96, 125, 139));
drawing.SetFill(fill);
```

# SetBorderColor

Sets annotation border color.

Inherited from [ApiBaseAnnotation.SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderColor.md).

## Syntax

```javascript
expression.SetBorderColor(color);
```

`expression` - A variable that represents an [ApiPolygonAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) |  | The border color. |

## Returns

boolean

## Example

Change the border color of an annotation in a PDF.

```javascript editor-pdf
// What color should the border of an annotation be in a PDF?

// Apply a color to the border outline of an annotation object in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
squareAnnot.SetBorderColor(Api.RGB(255, 0, 0));
```

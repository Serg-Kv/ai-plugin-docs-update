# SetFillColor

Sets annotation fill color.

Inherited from [ApiBaseAnnotation.SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetFillColor.md).

## Syntax

```javascript
expression.SetFillColor(color);
```

`expression` - A variable that represents an [ApiHighlightAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| color | Optional | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined |  | color to set fill (omit the argument to set no fill) |

## Returns

boolean

## Example

Set the background color of an annotation in a PDF.

```javascript editor-pdf
// Apply a fill color to make an annotation stand out in a PDF.

// Change the interior color of an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
squareAnnot.SetFillColor(Api.RGB(255, 0, 0));
```

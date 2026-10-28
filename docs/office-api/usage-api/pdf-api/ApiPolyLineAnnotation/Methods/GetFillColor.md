# GetFillColor

Gets annotation fill color.

Inherited from [ApiBaseAnnotation.GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetFillColor.md).

## Syntax

```javascript
expression.GetFillColor();
```

`expression` - A variable that represents an [ApiPolyLineAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined

## Example

Retrieve the fill color of an annotation in a PDF.

```javascript editor-pdf
// What color is used to fill an annotation in a PDF?

// Check the background or fill color applied to an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
squareAnnot.SetFillColor(Api.RGB(255, 0, 0));
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation fill color is: ${squareAnnot.GetFillColor()}`);
```

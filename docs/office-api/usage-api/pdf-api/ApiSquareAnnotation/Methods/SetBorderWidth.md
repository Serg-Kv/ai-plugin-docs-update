# SetBorderWidth

Sets annotation border width.

Inherited from [ApiBaseAnnotation.SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetBorderWidth.md).

## Syntax

```javascript
expression.SetBorderWidth(width);
```

`expression` - A variable that represents an [ApiSquareAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSquareAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| width | Required | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/pt.md) |  | The border width in points. |

## Returns

boolean

## Example

Change the thickness of an annotation's border in a PDF.

```javascript editor-pdf
// How thick should an annotation border be in a PDF?

// Set the width of the border outline on an annotation object in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
squareAnnot.SetBorderWidth(2);
```

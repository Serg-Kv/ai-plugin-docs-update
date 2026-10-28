# GetBorderColor

Gets annotation border color.

Inherited from [ApiBaseAnnotation.GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderColor.md).

## Syntax

```javascript
expression.GetBorderColor();
```

`expression` - A variable that represents an [ApiStrikeoutAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined

## Example

Check the border color of an annotation in a PDF.

```javascript editor-pdf
// How can I find the color of an annotation's outline in a PDF?

// Read the border color value from an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation border color is: ${squareAnnot.GetBorderColor()}`);
```

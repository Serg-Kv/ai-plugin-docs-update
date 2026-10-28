# GetDisplay

Gets annotation display type.

Inherited from [ApiBaseAnnotation.GetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetDisplay.md).

## Syntax

```javascript
expression.GetDisplay();
```

`expression` - A variable that represents an [ApiLinkAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLinkAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[DisplayType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DisplayType.md)

## Example

Retrieve the display preference setting of an annotation in a PDF.

```javascript editor-pdf
// How is the visibility of an annotation configured in a PDF?

// Check whether an annotation is displayed or hidden in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation display is: ${squareAnnot.GetDisplay()}`);
```

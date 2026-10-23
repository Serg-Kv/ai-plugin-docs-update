# GetRect

Gets annotation rect.

Inherited from [ApiBaseAnnotation.GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetRect.md).

## Syntax

```javascript
expression.GetRect();
```

`expression` - A variable that represents an [ApiPolyLineAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md)

## Example

Get the rectangular boundary of an annotation in a PDF.

```javascript editor-pdf
// What is the area occupied by an annotation in a PDF?

// Read the bounding rectangle coordinates of an annotation object in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation rect is: ${squareAnnot.GetRect()}`);
```

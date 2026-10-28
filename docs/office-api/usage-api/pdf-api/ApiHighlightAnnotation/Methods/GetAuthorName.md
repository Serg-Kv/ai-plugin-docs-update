# GetAuthorName

Gets annotation author name.

Inherited from [ApiBaseAnnotation.GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetAuthorName.md).

## Syntax

```javascript
expression.GetAuthorName();
```

`expression` - A variable that represents an [ApiHighlightAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

string

## Example

Read the author of an annotation in a PDF.

```javascript editor-pdf
// How can I find out who created an annotation in a PDF?

// Retrieve the name of the person who added an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation author name is: ${squareAnnot.GetAuthorName()}`);
```

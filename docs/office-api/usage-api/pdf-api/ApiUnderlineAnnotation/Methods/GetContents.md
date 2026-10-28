# GetContents

Gets annotation contents.

Inherited from [ApiBaseAnnotation.GetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetContents.md).

## Syntax

```javascript
expression.GetContents();
```

`expression` - A variable that represents an [ApiUnderlineAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnderlineAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

string \| null \| undefined

## Example

Retrieve the text or message inside an annotation in a PDF.

```javascript editor-pdf
// What text is stored in an annotation in a PDF?

// Read the content or description that was added to an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
squareAnnot.SetContents("Annot contents");
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation contents is: ${squareAnnot.GetContents()}`);
```

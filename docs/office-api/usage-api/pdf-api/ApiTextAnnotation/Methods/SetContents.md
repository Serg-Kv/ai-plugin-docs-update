# SetContents

Sets annotation contents.

Inherited from [ApiBaseAnnotation.SetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/SetContents.md).

## Syntax

```javascript
expression.SetContents(contents);
```

`expression` - A variable that represents an [ApiTextAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| contents | Required | string \| null \| undefined |  | The annotation text contents. |

## Returns

boolean

## Example

Add text content to an annotation in a PDF.

```javascript editor-pdf
// Store a message or note within an annotation in a PDF.

// Assign descriptive text to mark or label an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
let page = doc.GetPage(0);
page.AddObject(squareAnnot);
squareAnnot.SetContents("John Smith");
```

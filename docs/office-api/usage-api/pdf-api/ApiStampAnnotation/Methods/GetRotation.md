# GetRotation

Gets stamp rotate.

## Syntax

```javascript
expression.GetRotation();
```

`expression` - A variable that represents an [ApiStampAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[Degree](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Degree.md)

## Example

Find the angle of a stamp in a PDF.

```javascript editor-pdf
// How do I check how much a stamp is rotated in a PDF?

// See the rotation angle of a stamp annotation in a PDF.

let doc = Api.GetDocument();
let stampAnnot = Api.CreateStampAnnot([10, 10, 0, 0], 'D_Reviewed', 'Joe Doe');
let oldRotAngle = stampAnnot.GetRotation();
stampAnnot.SetScale(0.5);
stampAnnot.SetRotation(180);
let page = doc.GetPage(0);
page.AddObject(stampAnnot);
console.log(`We change stamp rotate angle from ${oldRotAngle} to: ${stampAnnot.GetRotation()}`);
```

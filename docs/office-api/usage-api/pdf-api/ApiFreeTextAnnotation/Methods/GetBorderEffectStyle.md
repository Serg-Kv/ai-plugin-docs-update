# GetBorderEffectStyle

Gets annotation border effect style.

Inherited from [ApiBaseAnnotation.GetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderEffectStyle.md).

## Syntax

```javascript
expression.GetBorderEffectStyle();
```

`expression` - A variable that represents an [ApiFreeTextAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[AnnotBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/AnnotBorderEffectStyle.md)

## Example

Retrieve the style of a border effect applied to an annotation in a PDF.

```javascript editor-pdf
// What type of border effect is applied to an annotation in a PDF?

// Find out whether an annotation has a cloud, solid, or other border effect style in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
squareAnnot.SetBorderEffectStyle("cloud");
squareAnnot.SetBorderEffectIntensity(1);

let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation border effect style is: ${squareAnnot.GetBorderEffectStyle()}`);
```

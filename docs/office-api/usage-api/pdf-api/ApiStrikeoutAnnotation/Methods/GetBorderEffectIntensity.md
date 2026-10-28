# GetBorderEffectIntensity

Gets annotation border effect intensity.

Inherited from [ApiBaseAnnotation.GetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation/Methods/GetBorderEffectIntensity.md).

## Syntax

```javascript
expression.GetBorderEffectIntensity();
```

`expression` - A variable that represents an [ApiStrikeoutAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

number

## Example

Retrieve the intensity level of a border effect on an annotation in a PDF.

```javascript editor-pdf
// What is the border effect intensity value for an annotation in a PDF?

// Check the strength of a cloud or other border effect applied to an annotation in a PDF.

let doc = Api.GetDocument();
let squareAnnot = Api.CreateSquareAnnot([10, 10, 160, 32]);
squareAnnot.SetBorderEffectStyle("cloud");
squareAnnot.SetBorderEffectIntensity(1);

let page = doc.GetPage(0);
page.AddObject(squareAnnot);
console.log(`Annotation border effect intensity is: ${squareAnnot.GetBorderEffectIntensity()}`);
```

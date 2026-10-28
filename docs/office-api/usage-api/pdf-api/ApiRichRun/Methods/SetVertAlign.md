# SetVertAlign

Specifies the alignment which will be applied to the contents of the run in relation to the default appearance of the run text:

Inherited from [ApiRichTextPr.SetVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr/Methods/SetVertAlign.md).

## Syntax

```javascript
expression.SetVertAlign(type);
```

`expression` - A variable that represents an [ApiRichRun](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [TextVertAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/TextVertAlign.md) |  | The vertical alignment type applied to the text contents. |

## Returns

[ApiRichTextPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRichTextPr.md)

## Example

Position text vertically as superscript or subscript in a PDF.

```javascript editor-pdf
// How do I raise or lower text vertically in a PDF?

// Apply vertical alignment to text in a PDF.

let doc = Api.GetDocument();
let freeTextAnnot = Api.CreateFreeTextAnnot([160, 50, 360, 135]);
let page = doc.GetPage(0);
page.AddObject(freeTextAnnot);
freeTextAnnot.SetIntent("freeTextCallout");
freeTextAnnot.SetCallout([{x: 161, y: 51}, {x: 249, y: 125}, {x: 261, y: 125}]);
freeTextAnnot.SetRectDiff([100, 64, 0.5, 0.5]);

let richContent = freeTextAnnot.GetContent();
let para = richContent.GetElement(0);
let run = para.GetElement(0);
run.AddText("Some example text");

let textPr = run.GetTextPr();
textPr.SetVertAlign("superscript");

console.log(`We set vert align property to ${textPr.GetVertAlign()} for rich text properties`);
```

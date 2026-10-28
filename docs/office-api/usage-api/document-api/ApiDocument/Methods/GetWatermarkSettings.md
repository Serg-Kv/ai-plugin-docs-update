# GetWatermarkSettings

Returns the watermark settings in the current document.

## Syntax

```javascript
expression.GetWatermarkSettings();
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiWatermarkSettings](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiWatermarkSettings.md)

## Example

Configure and update watermark settings on every page in a document.

```javascript editor-docx
// How do I change watermark text, font, and color in a document?

// Customize the appearance of a text watermark including style, size, and highlight before saving it.

let doc = Api.GetDocument();
let watermarkSettings = doc.GetWatermarkSettings();
watermarkSettings.SetType("text");
watermarkSettings.SetText("Example");
let textPr = watermarkSettings.GetTextPr();
textPr.SetFontFamily("Calibri");
textPr.SetFontSize(-1);
textPr.SetDoubleStrikeout(true);
textPr.SetItalic(true);
textPr.SetBold(true);
textPr.SetUnderline(true);
textPr.SetColor(Api.RGB(0, 255, 0));
textPr.SetHighlight("blue");
watermarkSettings.SetTextPr(textPr);
doc.SetWatermarkSettings(watermarkSettings);
```

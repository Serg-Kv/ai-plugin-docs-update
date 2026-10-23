# CreateCaretAnnot

Creates caret annotation.

## Syntax

```javascript
expression.CreateCaretAnnot(rect);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| rect | Required | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) \| [Quad](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Quad.md)[] |  | region to apply caret. |

## Returns

[ApiCaretAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCaretAnnotation.md)

## Example

Add a caret annotation to mark text insertions in a PDF.

```javascript editor-pdf
// How do I mark where text should be added in a PDF?

// Create an insertion point indicator in a PDF.

let doc = Api.GetDocument();
let caretAnnot = Api.CreateCaretAnnot([[85.04985826771654,56.70000000000001,229.27237795275593,56.70000000000001,85.04985826771654,70.9988031496063,229.27237795275593,70.9988031496063]]);
let page = doc.GetPage(0);
page.AddObject(caretAnnot);
```

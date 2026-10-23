# SetStartStyle

Sets a line start style.

## Syntax

```javascript
expression.SetStartStyle(style);
```

`expression` - A variable that represents an [ApiLineAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| style | Required | [LineEndStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/LineEndStyle.md) |  | The style of the line start endpoint. |

## Returns

boolean

## Example

Customize the start appearance of a line annotation in a PDF.

```javascript editor-pdf
// How do I change the start style in a PDF?

// Apply a specific line beginning to the annotation in a PDF.

let doc = Api.GetDocument();
let lineAnnot = Api.CreateLineAnnot([10, 10, 160, 32], {x: 15, y: 15}, {x: 155, y: 30});
lineAnnot.SetStartStyle("rClosedArrow");
let page = doc.GetPage(0);
page.AddObject(lineAnnot);
console.log(`Start style set to: ${lineAnnot.GetStartStyle()}`);
```

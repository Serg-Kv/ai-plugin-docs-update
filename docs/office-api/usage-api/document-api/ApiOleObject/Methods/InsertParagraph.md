# InsertParagraph

Inserts a paragraph at the specified position.

Inherited from [ApiDrawing.InsertParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing/Methods/InsertParagraph.md).

## Syntax

```javascript
expression.InsertParagraph(paragraph, sPosition, beRNewPara);
```

`expression` - A variable that represents an [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiOleObject.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| paragraph | Required | string \| [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) |  | Text or paragraph. |
| sPosition | Required | string |  | The position where the text or paragraph will be inserted ("before" or "after" the drawing specified). |
| beRNewPara | Required | boolean |  | Defines if this method returns a new paragraph (true) or the current ApiDrawing (false). |

## Returns

[ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) \| [ApiDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDrawing.md)

## Example

Insert a paragraph into the content area of a drawing in a document.

```javascript editor-docx
// How do I add text inside a shape in a document?

// Place a labeled paragraph inside a rectangle to annotate the shape in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This graphic object with paragraph.");
let fill = Api.CreateSolidFill(Api.RGB(255, 111, 61));
let stroke = Api.CreateStroke(0, Api.CreateNoFill());
let drawing = Api.CreateShape("rect", 3212465, 963295, fill, stroke);
paragraph.AddDrawing(drawing);
paragraph = Api.CreateParagraph();
paragraph.AddText("This is a new paragraph.");
drawing.InsertParagraph(paragraph);
```

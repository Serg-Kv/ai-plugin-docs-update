# SetBetweenBorder

Specifies the border which will be displayed between each paragraph in a set of paragraphs which have the same set of paragraph border settings.

Inherited from [ApiParaPr.SetBetweenBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetBetweenBorder.md).

## Syntax

```javascript
expression.SetBetweenBorder(type, size, space, color);
```

`expression` - A variable that represents an [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [BorderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/BorderType.md) |  | The border style. |
| size | Required | [pt_8](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt_8.md) |  | The width of the current border measured in eighths of a point. |
| space | Required | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt.md) |  | The spacing offset between the paragraphs measured in points used to place this border. |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) |  | The border color. |

## Returns

boolean

## Example

Add a visible border between adjacent paragraphs that share the same border settings in a document.

```javascript editor-docx
// How do I draw a dividing line between consecutive paragraphs in a document?

// Separate groups of related paragraphs with a styled border line for clearer visual structure in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is the first paragraph. We will add a thick orange border between it and the next paragraph. ");
paragraph.AddText("No additional spacing between the border and the paragraphs is added.");
paragraph.SetBetweenBorder("single", 24, 0, Api.Color(255, 111, 61));
paragraph = Api.CreateParagraph();
paragraph.AddText("This is the second paragraph. We will add a thin black border between it and the next paragraph. ");
paragraph.AddText("We added additional spacing between the border and the paragraphs.");
paragraph.SetBetweenBorder("single", 12, 10, Api.Color(51, 51, 51));
doc.Push(paragraph);
paragraph = Api.CreateParagraph();
paragraph.AddText("This is the third paragraph. The border can be displayed above it only, as there are no new paragraphs after it.");
doc.Push(paragraph);
```

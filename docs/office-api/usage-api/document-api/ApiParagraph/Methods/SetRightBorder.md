# SetRightBorder

Specifies the border which will be displayed at the right side of the page around the specified paragraph.

Inherited from [ApiParaPr.SetRightBorder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/SetRightBorder.md).

## Syntax

```javascript
expression.SetRightBorder(type, size, space, color);
```

`expression` - A variable that represents an [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [BorderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/BorderType.md) |  | The border style. |
| size | Required | [pt_8](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt_8.md) |  | The width of the current right border measured in eighths of a point. |
| space | Required | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/pt.md) |  | The spacing offset to the right of the paragraph measured in points used to place this border. |
| color | Required | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) |  | The border color. |

## Returns

boolean

## Example

Add a border to the right side of a paragraph in a document.

```javascript editor-docx
// How do I place a visible border along the right edge of a paragraph in a document?

// Decorate a paragraph with a colored line on its right side in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is the first paragraph. We will add a two point orange border at its right side. ");
paragraph.AddText("The space between the right side of the paragraph and the border is 8 points. ");
paragraph.AddText("These sentences are used to add lines for demonstrative purposes. ");
paragraph.AddText("These sentences are used to add lines for demonstrative purposes.");
paragraph.SetRightBorder("single", 16, 8, Api.Color(255, 111, 61));
```

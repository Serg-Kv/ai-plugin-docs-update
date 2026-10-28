# CreateShd

Creates the shading which can be applied to text, a paragraph, a table or a table cell.

## Syntax

```javascript
expression.CreateShd(type, color);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [ShdType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ShdType.md) |  | The shading type: **"nil"** - no shading, **"clear"** - solid fill. |
| color | Optional | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiColor.md) |  | The shading color. Required for the **"clear"** type. |

## Returns

[ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiShd.md)

## Example

Create a shading object and apply it to a paragraph in a document.

```javascript editor-docx
// Build the shading once with Api.CreateShd and pass it to the SetShd method in a document.

// Shade a paragraph with a light yellow background in a document.

const doc = Api.GetDocument();
const paragraph = doc.GetElement(0);
paragraph.AddText('This paragraph has a light yellow shading.');
const shd = Api.CreateShd('clear', Api.Color('#FFF2CC'));
paragraph.SetShd(shd);
```

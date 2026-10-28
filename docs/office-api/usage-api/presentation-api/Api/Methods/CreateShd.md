# CreateShd

Creates the shading which can be applied to text, a paragraph, a table or a table cell.

## Syntax

```javascript
expression.CreateShd(type, color);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| type | Required | [ShdType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/ShdType.md) |  | The shading type: **"nil"** - no shading, **"clear"** - solid fill. |
| color | Optional | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiColor.md) |  | The shading color. Required for the **"clear"** type. |

## Returns

[ApiShd](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiShd.md)

## Example

Create a shading object and apply it to table cells on a slide.

```javascript editor-pptx
// Build the shading once with Api.CreateShd and reuse it for several table cells on a slide.

// Shade the first row of a new table with the accent1 theme color on a slide.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);

const table = Api.CreateTable(2, 3);
const shd = Api.CreateShd('clear', Api.Color('accent1'));
const row = table.GetRow(0);
for (let i = 0; i < 3; i++) {
    row.GetCell(i).SetShd(shd);
}

slide.RemoveAllObjects();
slide.AddObject(table);
```

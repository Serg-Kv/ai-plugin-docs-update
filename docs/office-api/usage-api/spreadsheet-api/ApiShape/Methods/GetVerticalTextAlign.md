# GetVerticalTextAlign

Gets the vertical alignment from the shape content where a paragraph or text runs can be inserted.

## Syntax

```javascript
expression.GetVerticalTextAlign();
```

`expression` - A variable that represents an [ApiShape](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShape.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[VerticalTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/VerticalTextAlign.md)

## Example

Read the vertical text alignment of a shape in a spreadsheet.

```javascript editor-xlsx
// Useful for verifying vertical text placement before adjusting shape layout in a spreadsheet.

// Retrieve the current vertical alignment of a shape's inner content in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let fill = Api.CreateSolidFill(Api.RGB(255, 111, 61));
let stroke = Api.CreateStroke(0, Api.CreateNoFill());
let shape = worksheet.AddShape("flowChartOnlineStorage", 60 * 36000, 50 * 36000, fill, stroke, 0, 2 * 36000, 0, 3 * 36000);
let content = shape.GetContent();
content.RemoveAllElements();
shape.SetVerticalTextAlign("center");
let verticalAlign = shape.GetVerticalTextAlign();
let paragraph = Api.CreateParagraph();
paragraph.SetJc("left");
paragraph.AddText("The shape vertical text alignment is: " + verticalAlign);
content.Push(paragraph);
```

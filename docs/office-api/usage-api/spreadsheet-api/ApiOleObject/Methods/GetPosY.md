# GetPosY

Returns the y position of the current drawing on the worksheet.

Inherited from [ApiDrawing.GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing/Methods/GetPosY.md).

## Syntax

```javascript
expression.GetPosY();
```

`expression` - A variable that represents an [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md)

## Example

Get the vertical position of a shape in a spreadsheet.

```javascript editor-xlsx
// How do I find the top edge coordinate of a drawing in a spreadsheet?

// Read and display the Y position of a shape in a spreadsheet.

let worksheet = Api.GetActiveSheet();
let fill = Api.CreateSolidFill(Api.RGB(255, 111, 61));
let stroke = Api.CreateStroke(0, Api.CreateNoFill());
let drawing = worksheet.AddShape("flowChartOnlineStorage", 60 * 36000, 35 * 36000, fill, stroke, 0, 2 * 36000, 0, 3 * 36000);
drawing.SetPosition(2, 5 * 36000, 3, 2 * 36000);
let posY = drawing.GetPosY();
worksheet.GetRange("A1").SetValue("Drawing Y position: " + posY + " EMU");
```

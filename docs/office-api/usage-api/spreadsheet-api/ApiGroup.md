# ApiGroup

Class representing a group of drawings.

ApiGroup is a subclass of [ApiDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Copy.md) | [ApiGroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup.md) | Creates a copy of the current group. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Delete.md) | boolean | Deletes the specified drawing object. |
| [Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Fill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetClassType.md) | "group" | Returns a type of the ApiGroup class. |
| [GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetDescription.md) | string \| null | Gets the description of the current drawing. |
| [GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetFill.md) | [ApiFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill.md) \| null | Gets the fill formatting properties from the current graphic object. |
| [GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetFlipH.md) | boolean \| null | Get horizontal flip of current drawing. |
| [GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetFlipV.md) | boolean \| null | Get vertical flip of current drawing. |
| [GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetHeight.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the height of the current drawing. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetInternalId.md) | string | Returns an internal ID of the current drawing object. |
| [GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetLine.md) | [ApiStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke.md) \| null | Gets the outline properties from the current graphic object. |
| [GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetLockAspect.md) | boolean | Returns whether the aspect ratio of the drawing is locked. |
| [GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetLockValue.md) | boolean | Returns the lock value for the specified lock type of the current drawing. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetName.md) | string | Returns the name of the current drawing. |
| [GetParentSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetParentSheet.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) \| null \| undefined | Returns the parent sheet of the current drawing. |
| [GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosX.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the x position of the current drawing on the worksheet. |
| [GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosY.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the y position of the current drawing on the worksheet. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetPosition.md) | [DrawingCellAnchor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/DrawingCellAnchor.md) \| null | Returns the cell anchor of the current drawing; the offsets are limited by the anchor cell. |
| [GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetRotation.md) | number | Returns the rotation angle of the current drawing object. |
| [GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetShadow.md) | [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShadow.md) \| null | Returns the shadow of the current graphic object. |
| [GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetTextRange.md) | [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange.md) \| null | Returns a text range that covers the whole text of the current drawing. Creates a text body if the drawing does not yet have one. |
| [GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetTitle.md) | string \| null | Gets the title of the current drawing. |
| [GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/GetWidth.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the width of the current drawing. |
| [HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/HasTextContent.md) | boolean | Checks whether the current drawing has a text body. |
| [Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Select.md) | None | Selects the current graphic object. |
| [SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetDescription.md) | boolean | Sets the description of the current drawing. |
| [SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetFill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetFlipH.md) | boolean | Sets the horizontal flip of the current drawing. |
| [SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetFlipV.md) | boolean | Sets the vertical flip of the current drawing. |
| [SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetLine.md) | boolean | Sets the outline properties to the current graphic object. |
| [SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetLockAspect.md) | boolean | Sets whether the aspect ratio of the drawing is locked. |
| [SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetLockValue.md) | boolean | Sets the lock value to the specified lock type of the current drawing. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetName.md) | boolean | Sets the name of the current drawing. |
| [SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetOutLine.md) | boolean | Sets the outline properties to the specified graphic object. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetPosition.md) | None | Changes the position for the drawing object. |
| [SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetRotation.md) | boolean | Sets the rotation angle to the current drawing object. |
| [SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetShadow.md) | boolean | Sets the shadow to the current graphic object. |
| [SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetSize.md) | None | Sets a size of the object (image, shape, chart) bounding box. |
| [SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/SetTitle.md) | boolean | Sets the title of the current drawing. |
| [Ungroup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Ungroup.md) | [ApiDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing.md)[] \| null | Ungroups the current group of drawings. |
| [Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiGroup/Methods/Unselect.md) | boolean | Removes the current drawing from the selection. |

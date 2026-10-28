# ApiOleObject

Class representing an OLE object.

ApiOleObject is a subclass of [ApiDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiDrawing.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/Copy.md) | [ApiOleObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject.md) | Creates a copy of the current OLE object. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/Delete.md) | boolean | Deletes the specified drawing object. |
| [Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/Fill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [GetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetApplicationId.md) | string | Returns the application ID from the current OLE object. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetClassType.md) | "oleObject" | Returns a type of the ApiOleObject class. |
| [GetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetData.md) | string | Returns the string data from the current OLE object. |
| [GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetDescription.md) | string \| null | Gets the description of the current drawing. |
| [GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetFill.md) | [ApiFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFill.md) \| null | Gets the fill formatting properties from the current graphic object. |
| [GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetFlipH.md) | boolean \| null | Get horizontal flip of current drawing. |
| [GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetFlipV.md) | boolean \| null | Get vertical flip of current drawing. |
| [GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetHeight.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the height of the current drawing. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetInternalId.md) | string | Returns an internal ID of the current drawing object. |
| [GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetLine.md) | [ApiStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiStroke.md) \| null | Gets the outline properties from the current graphic object. |
| [GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetLockAspect.md) | boolean | Returns whether the aspect ratio of the drawing is locked. |
| [GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetLockValue.md) | boolean | Returns the lock value for the specified lock type of the current drawing. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetName.md) | string | Returns the name of the current drawing. |
| [GetParentSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetParentSheet.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) \| null \| undefined | Returns the parent sheet of the current drawing. |
| [GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosX.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the x position of the current drawing on the worksheet. |
| [GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosY.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the y position of the current drawing on the worksheet. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetPosition.md) | [DrawingCellAnchor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/DrawingCellAnchor.md) \| null | Returns the cell anchor of the current drawing; the offsets are limited by the anchor cell. |
| [GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetRotation.md) | number | Returns the rotation angle of the current drawing object. |
| [GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetShadow.md) | [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiShadow.md) \| null | Returns the shadow of the current graphic object. |
| [GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetTextRange.md) | [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTextRange.md) \| null | Returns a text range that covers the whole text of the current drawing. Creates a text body if the drawing does not yet have one. |
| [GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetTitle.md) | string \| null | Gets the title of the current drawing. |
| [GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/GetWidth.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/EMU.md) | Returns the width of the current drawing. |
| [HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/HasTextContent.md) | boolean | Checks whether the current drawing has a text body. |
| [Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/Select.md) | None | Selects the current graphic object. |
| [SetApplicationId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetApplicationId.md) | boolean | Sets the application ID to the current OLE object. |
| [SetData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetData.md) | boolean | Sets the data to the current OLE object. |
| [SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetDescription.md) | boolean | Sets the description of the current drawing. |
| [SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetFill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetFlipH.md) | boolean | Sets the horizontal flip of the current drawing. |
| [SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetFlipV.md) | boolean | Sets the vertical flip of the current drawing. |
| [SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetLine.md) | boolean | Sets the outline properties to the current graphic object. |
| [SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetLockAspect.md) | boolean | Sets whether the aspect ratio of the drawing is locked. |
| [SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetLockValue.md) | boolean | Sets the lock value to the specified lock type of the current drawing. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetName.md) | boolean | Sets the name of the current drawing. |
| [SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetOutLine.md) | boolean | Sets the outline properties to the specified graphic object. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetPosition.md) | None | Changes the position for the drawing object. |
| [SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetRotation.md) | boolean | Sets the rotation angle to the current drawing object. |
| [SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetShadow.md) | boolean | Sets the shadow to the current graphic object. |
| [SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetSize.md) | None | Sets a size of the object (image, shape, chart) bounding box. |
| [SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/SetTitle.md) | boolean | Sets the title of the current drawing. |
| [Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiOleObject/Methods/Unselect.md) | boolean | Removes the current drawing from the selection. |

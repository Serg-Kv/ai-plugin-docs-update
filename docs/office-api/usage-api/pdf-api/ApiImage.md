# ApiImage

Class representing an image.

ApiImage is a subclass of [ApiDrawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Copy.md) | [ApiImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage.md) | Creates a copy of the current image. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Delete.md) | boolean | Deletes the specified drawing object from the parent. |
| [Fill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Fill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetClassType.md) | "image" | Returns the type of the ApiImage class. |
| [GetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetDescription.md) | string \| null | Gets the description of the current drawing. |
| [GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFill.md) | [ApiFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFill.md) \| null | Gets the fill formatting properties from the current graphic object. |
| [GetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFlipH.md) | boolean \| null | Get horizontal flip of current drawing. |
| [GetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetFlipV.md) | boolean \| null | Get vertical flip of current drawing. |
| [GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetHeight.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) | Returns the height of the current drawing. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetInternalId.md) | string | Returns an internal ID of the current drawing. |
| [GetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLine.md) | [ApiStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStroke.md) \| null | Gets the outline properties from the current graphic object. |
| [GetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLockAspect.md) | boolean | Returns whether the aspect ratio of the drawing is locked. |
| [GetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetLockValue.md) | boolean | Returns the lock value for the specified lock type of the current drawing. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetName.md) | string | Returns the name of the current drawing. |
| [GetParentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetParentPage.md) | [ApiPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md) \| null \| undefined | Returns the type of the ApiDrawing class. |
| [GetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetPosX.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) | Gets the x position of the drawing on the page. |
| [GetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetPosY.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) | Gets the y position of the drawing on the page. |
| [GetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetRotation.md) | number | Returns the rotation angle of the current drawing object. |
| [GetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetShadow.md) | [ApiShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiShadow.md) \| null | Returns the shadow of the current graphic object. |
| [GetTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetTextRange.md) | [ApiTextRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextRange.md) \| null | Returns a text range that covers the whole text of the current drawing. Creates a text body if the drawing does not yet have one. |
| [GetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetTitle.md) | string \| null | Gets the title of the current drawing. |
| [GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/GetWidth.md) | [EMU](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/EMU.md) | Returns the width of the current drawing. |
| [HasTextContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/HasTextContent.md) | boolean | Checks whether the current drawing has a text body. |
| [Select](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Select.md) | boolean | Selects the current graphic object. |
| [SetDescription](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetDescription.md) | boolean | Sets the description of the current drawing. |
| [SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFill.md) | boolean | Sets the fill formatting properties to the current graphic object. |
| [SetFlipH](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFlipH.md) | boolean | Sets the horizontal flip of the current drawing. |
| [SetFlipV](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetFlipV.md) | boolean | Sets the vertical flip of the current drawing. |
| [SetLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLine.md) | boolean | Sets the outline properties to the current graphic object. |
| [SetLockAspect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLockAspect.md) | boolean | Sets whether the aspect ratio of the drawing is locked. |
| [SetLockValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetLockValue.md) | boolean | Sets the lock value to the specified lock type of the current drawing. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetName.md) | boolean | Sets the name of the current drawing. If another drawing with the same name already exists, that drawing's name will be reset to a default auto-generated name. OLE objects do not support a custom name, so for them this method always returns false. |
| [SetOutLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetOutLine.md) | boolean | Sets the outline properties to the current graphic object. |
| [SetPosX](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetPosX.md) | boolean | Sets the x position of the drawing on the page. |
| [SetPosY](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetPosY.md) | boolean | Sets the y position of the drawing on the page. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetPosition.md) | boolean | Sets the position of the drawing on the page. |
| [SetRotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetRotation.md) | boolean | Sets the rotation angle to the current drawing object. |
| [SetShadow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetShadow.md) | boolean | Sets the shadow to the current graphic object. |
| [SetSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetSize.md) | boolean | Sets the size of the object (image, shape, chart) bounding box. |
| [SetTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/SetTitle.md) | boolean | Sets the title of the current drawing. |
| [Unselect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiImage/Methods/Unselect.md) | boolean | Removes the current graphic object from the selection. |

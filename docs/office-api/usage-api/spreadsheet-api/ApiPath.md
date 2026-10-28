# ApiPath

Class representing a path in geometry.

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [ArcTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/ArcTo.md) | None | Draws an arc from the current point using the specified width and height radii, start angle, and sweep angle. |
| [Close](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/Close.md) | None | Closes the current path. |
| [CubicBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/CubicBezTo.md) | None | Draws a cubic Bezier curve from the current point to the specified end point using two control points. |
| [GetCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommand.md) | [ApiPathCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand.md) \| null | Returns a specific path command by its index. |
| [GetCommandCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommandCount.md) | number | Returns the number of commands for the current path. |
| [GetCommands](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetCommands.md) | [ApiPathCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPathCommand.md)[] | Returns all commands of the current path. |
| [GetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetFill.md) | [PathFillType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PathFillType.md) | Returns the fill type of the current path. |
| [GetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetHeight.md) | number | Returns the height of the current path. |
| [GetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetStroke.md) | boolean | Returns true if the current path is stroked, otherwise false. |
| [GetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/GetWidth.md) | number | Returns the width of the current path. |
| [LineTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/LineTo.md) | None | Draws a line from the current point to the specified coordinates. |
| [MoveTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/MoveTo.md) | None | Moves the current path to the specified coordinates. |
| [QuadBezTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/QuadBezTo.md) | None | Draws a quadratic Bezier curve from the current point to the specified end point using a control point. |
| [SetFill](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetFill.md) | None | Sets the fill type to the current path. |
| [SetHeight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetHeight.md) | None | Sets the height to the current path. |
| [SetStroke](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetStroke.md) | None | Sets whether the current path is stroked. |
| [SetWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPath/Methods/SetWidth.md) | None | Sets the width to the current path. |

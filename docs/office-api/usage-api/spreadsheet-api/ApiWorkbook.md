# ApiWorkbook

Class representing the currently active workbook

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| TableStyles | ApiTableStyles | Returns the collection of table styles of the workbook. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [BreakLink](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/BreakLink.md) | boolean | Breaks the link to the specified workbook: the formulas that refer to it are replaced with their current values, and the link is removed from the workbook. |
| [Calculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Calculate.md) | boolean | Recalculates the cells that need recalculation (changed, added or volatile) across the workbook. Forces the recalc that is otherwise deferred until a macro finishes, so up-to-date formula results can be read within the same macro. |
| [GetActiveChart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetActiveChart.md) | [ApiChart](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiChart.md) \| null | Returns the active chart of the workbook. |
| [GetActiveSheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetActiveSheet.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the active sheet of the workbook. |
| [GetAllPivotTables](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetAllPivotTables.md) | [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md)[] | Returns all pivot tables in the workbook. |
| [GetCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetCustomProperties.md) | [ApiCustomProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCustomProperties.md) | Returns the custom properties of the workbook. |
| [GetDrawingsByName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetDrawingsByName.md) | [Drawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/Drawing.md)[] | Returns drawings with the specified names from the workbook. |
| [GetLinkSources](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetLinkSources.md) | string[] | Returns the paths of the other workbooks registered as external links of the current workbook, including links no formula uses any longer. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetName.md) | string | Returns the name of the workbook. |
| [GetSheets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetSheets.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md)[] | Returns a sheet collection that represents all the sheets in the workbook. |
| [GetTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/GetTheme.md) | [ApiTheme](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTheme.md) | Returns the theme of the workbook. |
| [Redraw](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Redraw.md) | boolean | Redraws the editor screen, making the changes already made by a macro visible without waiting for it to finish. Observable from asynchronous code only. Repaints without recalculating: call [ApiWorkbook#Calculate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Calculate.md) first if formula results must be up to date. |
| [Save](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorkbook/Methods/Save.md) | None | Saves changes to the specified document. |

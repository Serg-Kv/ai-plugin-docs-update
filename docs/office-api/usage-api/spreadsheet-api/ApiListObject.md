# ApiListObject

Class representing a formatted table.

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Active | boolean | Indicates whether the active cell is within the table range. |
| AlternativeText | string | Returns or sets the alternative text for the table. |
| AutoFilter | [ApiAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter.md) \| null | Returns the AutoFilter object for the table, or null. |
| Comment | string | Returns or sets the comment (summary alternative text) for the table. |
| DataBodyRange | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the data rows. |
| DisplayName | string | Returns or sets the display name of the table. |
| HeaderRowRange | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the header row. |
| Name | string | Returns or sets the name of the table. |
| Parent | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the parent worksheet. |
| Range | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the table. |
| ShowAutoFilter | boolean | Returns or sets whether the AutoFilter is present. |
| ShowAutoFilterDropDown | boolean | Returns or sets whether the AutoFilter dropdown arrows are shown. |
| ShowHeaders | boolean | Returns or sets whether the header row is displayed. |
| ShowTableStyleColumnStripes | boolean | Returns or sets whether column stripes are applied. |
| ShowTableStyleFirstColumn | boolean | Returns or sets whether the first column style is applied. |
| ShowTableStyleLastColumn | boolean | Returns or sets whether the last column style is applied. |
| ShowTableStyleRowStripes | boolean | Returns or sets whether row stripes are applied. |
| ShowTotals | boolean | Returns or sets whether the totals row is displayed. |
| Sort | [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) | Returns the Sort object associated with the table. |
| SourceType | [XlListObjectSourceType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlListObjectSourceType.md) | Returns the data source type of the table. |
| Summary | string | Returns or sets the description of the table. |
| TableStyle | string | Returns or sets the name of the table style. |
| TotalsRowRange | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the totals row; null if not shown. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/AddListColumn.md) | [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md) \| null | Adds a new column to the table at the specified 1-based position. |
| [AddListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/AddListRow.md) | [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md) \| null | Adds a new data row to the table at the specified 1-based position. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Delete.md) | None | Deletes the ListObject object and clears the cell formatting. |
| [GetActive](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetActive.md) | boolean | Returns a Boolean value that indicates whether the ListObject is active. The ListObject is considered active when the active cell is within the range of the ListObject. |
| [GetAlternativeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetAlternativeText.md) | string | Returns the alternative text for the table. |
| [GetAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetAutoFilter.md) | [ApiAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiAutoFilter.md) \| null | Returns the ApiAutoFilter object representing the autofilter applied to the table. |
| [GetComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetComment.md) | string | Returns the comment (summary alternative text) for the table. |
| [GetDataBodyRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetDataBodyRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the data rows in the table, excluding the header row and totals row. |
| [GetDisplayName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetDisplayName.md) | string | Returns the display name of the table. |
| [GetHeaderRowRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetHeaderRowRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the header row of the table. |
| [GetListColumns](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetListColumns.md) | [ApiListColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListColumn.md)[] | Returns an array of all columns in the table. |
| [GetListRows](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetListRows.md) | [ApiListRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListRow.md)[] | Returns an array of all data rows in the table, excluding the header and totals rows. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetName.md) | string | Returns the name of the table. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetParent.md) | [ApiWorksheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiWorksheet.md) | Returns the ApiWorksheet object that is the parent of the table. |
| [GetRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the ApiRange object that represents the range of the table. |
| [GetShowAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowAutoFilter.md) | boolean | Returns whether the AutoFilter dropdown buttons are displayed on the header row of the table. |
| [GetShowAutoFilterDropDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowAutoFilterDropDown.md) | boolean | Returns whether the AutoFilter dropdown arrows are displayed on the header row of the table. |
| [GetShowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowHeaders.md) | boolean | Returns whether the header row is displayed for the table. |
| [GetShowTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleColumnStripes.md) | boolean | Returns whether banded column formatting is applied to the table. |
| [GetShowTableStyleFirstColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleFirstColumn.md) | boolean | Returns whether the first column formatting is applied to the table. |
| [GetShowTableStyleLastColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleLastColumn.md) | boolean | Returns whether the last column formatting is applied to the table. |
| [GetShowTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTableStyleRowStripes.md) | boolean | Returns whether banded row formatting is applied to the table. |
| [GetShowTotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetShowTotals.md) | boolean | Returns whether the totals row is displayed for the table. |
| [GetSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSort.md) | [ApiSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiSort.md) | Returns the Sort object for this list object. |
| [GetSourceType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSourceType.md) | string | Returns the source type of the table. |
| [GetSummary](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetSummary.md) | string | Returns the summary description (alternative text summary) for the table. |
| [GetTableStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetTableStyle.md) | string | Returns the name of the table style applied to the table. |
| [GetTotalsRowRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/GetTotalsRowRange.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of the totals row of the table. |
| [Resize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Resize.md) | None | Resizes the ListObject to a new range. |
| [SetAlternativeText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetAlternativeText.md) | None | Sets the alternative text for the table. |
| [SetComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetComment.md) | None | Sets the comment (summary alternative text) for the table. |
| [SetDisplayName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetDisplayName.md) | boolean | Sets the display name of the table. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetName.md) | boolean | Sets the name of the table. |
| [SetShowAutoFilter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowAutoFilter.md) | None | Sets whether the AutoFilter is present on the table. |
| [SetShowAutoFilterDropDown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowAutoFilterDropDown.md) | None | Sets whether the AutoFilter dropdown arrows are displayed on the header row of the table. |
| [SetShowHeaders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowHeaders.md) | None | Sets whether the header row is displayed for the table. |
| [SetShowTableStyleColumnStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleColumnStripes.md) | None | Sets whether banded column formatting is applied to the table. |
| [SetShowTableStyleFirstColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleFirstColumn.md) | None | Sets whether the first column formatting is applied to the table. |
| [SetShowTableStyleLastColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleLastColumn.md) | None | Sets whether the last column formatting is applied to the table. |
| [SetShowTableStyleRowStripes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTableStyleRowStripes.md) | None | Sets whether banded row formatting is applied to the table. |
| [SetShowTotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetShowTotals.md) | None | Sets whether the totals row is displayed for the table. |
| [SetSummary](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetSummary.md) | None | Sets the summary description (alternative text summary) for the table. |
| [SetTableStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/SetTableStyle.md) | None | Sets the table style by name. Built-in table style names: TableStyleLight1-21, TableStyleMedium1-28, TableStyleDark1-11. |
| [Unlist](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiListObject/Methods/Unlist.md) | None | Removes the list functionality from the ListObject and converts it to a regular data range. |

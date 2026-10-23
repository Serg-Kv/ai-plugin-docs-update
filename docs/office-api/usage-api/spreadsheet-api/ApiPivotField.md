# ApiPivotField

Class representing a pivot table field.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AutoSortField | string | Returns the name of the field that is used to sort the specified field. |
| AutoSortOrder | [SortOrder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/SortOrder.md) | Returns the sort order for the specified field. |
| Caption | string | Returns or sets a value that represents the label text for the pivot field. |
| CurrentPage | string \| number | Returns the current page which is displayed for the page field (valid only for page fields). |
| DragToColumn | boolean | Returns or sets the setting which specifies whether the specified field can be dragged to the column position. |
| DragToData | boolean | Returns or sets the setting which specifies whether the specified field can be dragged to the data position. |
| DragToPage | boolean | Returns or sets the setting which specifies whether the specified field can be dragged to the page position. |
| DragToRow | boolean | Returns or sets the setting which specifies whether the specified field can be dragged to the row position. |
| Formula | number | Returns or sets a value that represents the object's formula. |
| Index | number | Returns an index for the pivot table field. |
| LayoutBlankLine | boolean | Returns and sets the setting which specifies whether to insert blank rows after each item. |
| LayoutCompactRow | boolean | Returns or sets the setting which specifies whether a pivot table field is compacted. |
| LayoutForm | number | Returns or sets the way the specified pivot table items appear — in table format or in outline format. |
| LayoutPageBreak | boolean | Returns or sets the setting which specifies whether to insert a page break after each field. |
| LayoutSubtotalLocation | number | Returns or sets the layout subtotal location. |
| LayoutSubtotals | boolean | Returns or sets the setting which specifies whether to show subtotals. |
| Name | string | Returns or sets a value representing the object name. |
| NumberFormat | string \| null | Returns or sets a value that represents the format code for the object. |
| Orientation | number | Returns or sets a pivot field orientation value that represents the location of the field in the specified pivot table report. |
| Parent | [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md) | Returns the parent object for the current field. |
| PivotFilters | [ApiPivotFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotFilters.md) | Returns an object that represents the filters for the specified field. |
| PivotItems | [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md) \| [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md)[] | Returns an object that represents either a single pivot table item (the ApiPivotItem object) or a collection of all the visible and hidden items (an array of the ApiPivotItem objects) in the specified field. |
| Position | number | Returns or sets a value that represents the position of the field (first, second, third, and so on) among all the fields in its orientation (Rows, Columns, Pages, Data). |
| RepeatLabels | boolean | Returns or sets the setting which specifies whether to repeat items labels at each row. |
| ShowAllItems | boolean | Returns or sets the setting which specifies whether to show items with no data. |
| ShowingInAxis | boolean | Returns the setting which specifies whether the pivot table field is currently visible in the pivot table. |
| SourceName | string | Returns a source name for the pivot table field. |
| SubtotalName | string | Returns or sets the text label displayed in the subtotal column or row heading in the specified pivot table report. |
| Subtotals | object | Returns or sets the subtotals. |
| Table | [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md) | Returns the ApiPivotTable object which represents the pivot table for the current field. |
| Value | string | Returns or sets a value representing the name of the specified field in the pivot table report. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AutoSort](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/AutoSort.md) | None | Establishes automatic field-sorting rules for the pivot table reports. |
| [ClearAllFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearAllFilters.md) | None | Deletes all filters currently applied to the pivot field. |
| [ClearLabelFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearLabelFilters.md) | None | Deletes all label filters or all date filters from the pivot filters collection. |
| [ClearManualFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearManualFilters.md) | None | Deletes all manual filters from the pivot filters collection. |
| [ClearValueFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/ClearValueFilters.md) | None | Deletes all value filters from the pivot filters collection. |
| [GetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetCaption.md) | string | Returns a value that represents the label text for the pivot field. |
| [GetCurrentPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetCurrentPage.md) | string \| number | Returns the current page which is displayed for the page field (valid only for page fields). |
| [GetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToColumn.md) | boolean | Returns the setting which specifies whether the specified field can be dragged to the column position. |
| [GetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToData.md) | boolean | Returns the setting which specifies whether the specified field can be dragged to the data position. |
| [GetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToPage.md) | boolean | Returns the setting which specifies whether the specified field can be dragged to the page position. |
| [GetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetDragToRow.md) | boolean | Returns the setting which specifies whether the specified field can be dragged to the row position. |
| [GetIndex](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetIndex.md) | number | Returns an index for the pivot table field. |
| [GetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutBlankLine.md) | boolean | Returns the setting which specifies whether to insert blank rows after each item. |
| [GetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutCompactRow.md) | boolean | Returns the setting which specifies whether a pivot table field is compacted. |
| [GetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutForm.md) | [PivotLayoutType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotLayoutType.md) | Returns the way the specified pivot table items appear — in table format or in outline format. |
| [GetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutPageBreak.md) | boolean | Returns the setting which specifies whether to insert a page break after each field. |
| [GetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutSubtotalLocation.md) | [LayoutSubtotalLocationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/LayoutSubtotalLocationType.md) | Returns the layout subtotal location. |
| [GetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetLayoutSubtotals.md) | boolean | Returns the setting which specifies whether to show subtotals. |
| [GetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetName.md) | string | Returns a value representing the object name. |
| [GetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetOrientation.md) | [PivotFieldOrientationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotFieldOrientationType.md) | Returns a pivot field orientation value that represents the location of the field in the specified pivot table report. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetParent.md) | [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md) | Returns the parent object for the current field. |
| [GetPivotFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPivotFilters.md) | [ApiPivotFilters](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotFilters.md) | Returns the collection of pivot filters applied to the specified pivot field. |
| [GetPivotItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPivotItems.md) | [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md)[] \| [ApiPivotItem](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotItem.md) \| null | Returns an object that represents either a single pivot table item (the ApiPivotItem object) or a collection of all the visible and hidden items (an array of the ApiPivotItem objects) in the specified field. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetPosition.md) | number | Returns a value that represents the position of the field (first, second, third, and so on) among all the fields in its orientation (Rows, Columns, Pages, Data). |
| [GetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetRepeatLabels.md) | boolean | Returns the setting which specifies whether to repeat items labels at each row. |
| [GetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetShowAllItems.md) | boolean | Returns the setting which specifies whether to show items with no data. |
| [GetShowingInAxis](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetShowingInAxis.md) | boolean | Returns the setting which specifies whether the pivot table field is currently visible in the pivot table. |
| [GetSourceName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSourceName.md) | string | Returns a source name for the pivot table field. |
| [GetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSubtotalName.md) | string | Returns the text label displayed in the subtotal column or row heading in the specified pivot table report. |
| [GetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetSubtotals.md) | [PivotFieldSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/PivotFieldSubtotals.md) | Returns an object that represents all subtotals. |
| [GetTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetTable.md) | [ApiPivotTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotTable.md) | Returns the ApiPivotTable object which represents the pivot table for the current field. |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/GetValue.md) | string | Returns a value representing the name of the specified field in the pivot table report. |
| [Group](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Group.md) | boolean | Groups the dates of the pivot table field by periods or its numbers by intervals, as VBA Range.Group does for a cell of the field. The field must be in the rows or columns; grouping again replaces the previous grouping of the field. For dates, the field shows the shortest period, and a new field is added next to it for every longer one. |
| [Move](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Move.md) | None | Moves the current pivot field inside the category. |
| [Remove](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/Remove.md) | None | Removes the current pivot field from the pivot table. |
| [SetCaption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetCaption.md) | None | Sets a value that represents the label text for the pivot field. |
| [SetDragToColumn](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToColumn.md) | None | Sets the setting which specifies whether the specified field can be dragged to the column position. |
| [SetDragToData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToData.md) | None | Sets the setting which specifies whether the specified field can be dragged to the data position. |
| [SetDragToPage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToPage.md) | None | Sets the setting which specifies whether the specified field can be dragged to the page position. |
| [SetDragToRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetDragToRow.md) | None | Sets the setting which specifies whether the specified field can be dragged to the row position. |
| [SetLayoutBlankLine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutBlankLine.md) | None | Sets the setting which specifies whether to insert blank rows after each item. |
| [SetLayoutCompactRow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutCompactRow.md) | None | Sets the setting which specifies whether a pivot table field is compacted. |
| [SetLayoutForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutForm.md) | None | Sets the way the specified pivot table items appear — in table format or in outline format. |
| [SetLayoutPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutPageBreak.md) | None | Sets the setting which specifies whether to insert a page break after each field. |
| [SetLayoutSubtotalLocation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutSubtotalLocation.md) | None | Sets the layout subtotal location. |
| [SetLayoutSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetLayoutSubtotals.md) | None | Sets the setting which specifies whether to show subtotals. |
| [SetName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetName.md) | None | Sets a value representing the object name. |
| [SetOrientation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetOrientation.md) | None | Sets a pivot field orientation value that represents the location of the field in the specified pivot table report. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetPosition.md) | None | Sets a value that represents the position of the field (first, second, third, and so on) among all the fields in its orientation (Rows, Columns, Pages, Data). |
| [SetRepeatLabels](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetRepeatLabels.md) | None | Sets the setting which specifies whether to repeat items labels at each row. |
| [SetShowAllItems](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetShowAllItems.md) | None | Sets the setting which specifies whether to show items with no data. |
| [SetSubtotalName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetSubtotalName.md) | None | Sets the text label displayed in the subtotal column or row heading in the specified pivot table report. |
| [SetSubtotals](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetSubtotals.md) | None | Sets an object that represents all subtotals. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiPivotField/Methods/SetValue.md) | None | Sets a value representing the name of the specified field in the pivot table report. |

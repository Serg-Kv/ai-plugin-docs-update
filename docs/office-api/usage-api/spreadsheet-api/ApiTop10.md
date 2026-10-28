# ApiTop10

Class representing a top 10 conditional formatting rule.

ApiTop10 is a subclass of [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Percent | boolean | Returns or sets whether the top 10 ranking is percentage-based. |
| Rank | number | Returns or sets the rank value of the top 10 condition. |
| TopBottom | [XlTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTopBottom.md) | Returns or sets the "XlTopBottom" constant indicating whether the ranking is evaluated from the top or bottom. |
| Type | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the top 10 conditional formatting rule. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/Delete.md) | None | Deletes the top 10 conditional formatting rule. |
| [GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetAppliesTo.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the range of cells to which the current conditional formatting rule applies. |
| [GetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetDateOperator.md) | [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) \| null | Returns the date operator for time period conditions. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| null | Returns the fill color for the top 10 conditional formatting rule. |
| [GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFont.md) | [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) | Returns the font formatting for the top 10 conditional formatting rule. |
| [GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFormula1.md) | string | Returns the first formula used by the current conditional formatting rule. |
| [GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetFormula2.md) | string | Returns the second formula used by the current conditional formatting rule. |
| [GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetNumberFormat.md) | string | Returns the number format for the top 10 conditional formatting rule. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetOperator.md) | [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) | Returns the format condition operator. |
| [GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPTCondition.md) | PTCondition \| null | Returns the pivot table condition object. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetParent.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object of the current format condition. |
| [GetPercent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPercent.md) | boolean | Returns whether the top 10 ranking is percentage-based. |
| [GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetPriority.md) | number | Returns the priority value of the conditional formatting rule. |
| [GetRank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetRank.md) | number | Returns the rank value for the top 10 condition. |
| [GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetScopeType.md) | [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) | Returns the scope type of the conditional formatting rule. |
| [GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetStopIfTrue.md) | boolean | Returns whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetText.md) | string | Returns the text value used in text-based conditional formatting rules. |
| [GetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetTextOperator.md) | [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) \| null | Returns the text operator for text-based conditional formatting rules. |
| [GetTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetTopBottom.md) | [XlTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTopBottom.md) | Returns the "XlTopBottom" constant indicating whether the ranking is evaluated from the top or bottom. |
| [GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/GetType.md) | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the top 10 conditional formatting rule. |
| [Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/Modify.md) | [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md) \| null | Modifies the current format condition with the specified parameters. |
| [ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/ModifyAppliesToRange.md) | None | Modifies the cell range to which the current conditional formatting rule applies. |
| [SetBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetBorders.md) | None | Sets the border style for the conditional formatting rule. |
| [SetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetDateOperator.md) | None | Sets the date operator for time period conditions. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetFillColor.md) | None | Sets the fill color for the top 10 conditional formatting rule. |
| [SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetFirstPriority.md) | None | Sets the priority value for the current conditional formatting rule to "1" so that it will be evaluated before all other rules on the worksheet. |
| [SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetLastPriority.md) | None | Sets the evaluation order for the current conditional formatting rule so it is evaluated after all other rules on the worksheet. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetNumberFormat.md) | None | Sets the number format for the top 10 conditional formatting rule. |
| [SetPercent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetPercent.md) | None | Sets whether the top 10 ranking is percentage-based. |
| [SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetPriority.md) | None | Sets the priority value for the conditional formatting rule. |
| [SetRank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetRank.md) | None | Sets the rank value for the top 10 condition. |
| [SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetScopeType.md) | None | Sets the scope type for the conditional formatting rule. |
| [SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetStopIfTrue.md) | None | Sets whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetText.md) | None | Sets the text value used in text-based conditional formatting rules. |
| [SetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetTextOperator.md) | None | Sets the text operator for text-based conditional formatting rules. |
| [SetTopBottom](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiTop10/Methods/SetTopBottom.md) | None | Sets the "XlTopBottom" constant indicating whether the ranking is evaluated from the top or bottom. |

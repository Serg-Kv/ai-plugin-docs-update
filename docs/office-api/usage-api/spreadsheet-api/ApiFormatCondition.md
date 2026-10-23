# ApiFormatCondition

Class representing a single format condition.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AboveBelow | boolean | Returns or sets whether the condition applies above or below the average. |
| AppliesTo | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the range to which this condition applies. |
| DateOperator | [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) | Returns or sets the date operator for time period conditions. |
| FillColor | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| 'No Fill' | Returns or sets the background color of the format condition. |
| Font | [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) \| null | Returns the font applied by the format condition. |
| Formula1 | string | Returns or sets the first formula used by the format condition. |
| Formula2 | string | Returns or sets the second formula used by the format condition. |
| NumberFormat | string | Returns or sets the number format applied to a cell when the conditional formatting rule evaluates to true. |
| Operator | [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) | Returns the format condition operator. |
| PTCondition | PTCondition | Returns the pivot table condition object. |
| Parent | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object of the format condition. |
| PercentRank | boolean | Returns or sets whether the rank is percentage-based. |
| Priority | number | Returns or sets the priority of the condition. |
| Rank | number | Returns or sets the rank for top/bottom conditional formatting rules. |
| ScopeType | [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) | Returns or sets the scope type for the format condition. |
| StdDev | number | Returns or sets the number of standard deviations for average conditions. |
| StopIfTrue | boolean | Returns or sets whether subsequent conditional formatting rules should be evaluated when this rule evaluates to true. |
| Text | string | Returns or sets the text for text-based conditions. |
| TextOperator | [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) | Returns or sets the text operator for text-based conditions. |
| Type | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the format condition type. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/Delete.md) | None | Deletes the current format condition. |
| [GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetAppliesTo.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) \| null | Returns the range of cells to which the current conditional formatting rule applies. |
| [GetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetDateOperator.md) | [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) \| null | Returns the date operator for time period conditions. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| 'No Fill' | Returns the background color for the format condition. |
| [GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFont.md) | [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) \| null | Returns the font applied by the current format condition. |
| [GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFormula1.md) | string | Returns the first formula used by the current conditional formatting rule. |
| [GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetFormula2.md) | string | Returns the second formula used by the current conditional formatting rule. |
| [GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetNumberFormat.md) | string | Returns the number format applied to a cell when the conditional formatting rule evaluates to true. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetOperator.md) | [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) | Returns the format condition operator. |
| [GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetPTCondition.md) | PTCondition \| null | Returns the pivot table condition object. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetParent.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object of the current format condition. |
| [GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetPriority.md) | number | Returns the priority value of the conditional formatting rule. |
| [GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetScopeType.md) | [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) | Returns the scope type of the conditional formatting rule. |
| [GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetStopIfTrue.md) | boolean | Returns whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetText.md) | string | Returns the text value used in text-based conditional formatting rules. |
| [GetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetTextOperator.md) | [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) \| null | Returns the text operator for text-based conditional formatting rules. |
| [GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/GetType.md) | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the format condition type. |
| [Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/Modify.md) | [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md) \| null | Modifies the current format condition with the specified parameters. |
| [ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/ModifyAppliesToRange.md) | None | Sets the cell range to which the current conditional formatting rule applies. |
| [SetBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetBorders.md) | None | Sets the border style for the conditional formatting rule. |
| [SetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetDateOperator.md) | None | Sets the date operator for time period conditions. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetFillColor.md) | None | Sets the background color to the format condition with the previously created color object. |
| [SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetFirstPriority.md) | None | Sets the priority value for the current conditional formatting rule to "1" so that it will be evaluated before all other rules on the worksheet. |
| [SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetLastPriority.md) | None | Sets the evaluation order for the current conditional formatting rule so it is evaluated after all other rules on the worksheet. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetNumberFormat.md) | None | Sets the number format applied to a cell when the conditional formatting rule evaluates to true. |
| [SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetPriority.md) | None | Sets the priority value of the conditional formatting rule. |
| [SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetScopeType.md) | None | Sets the scope type for the conditional formatting rule. |
| [SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetStopIfTrue.md) | None | Sets whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetText.md) | None | Sets the text value used in text-based conditional formatting rules. |
| [SetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition/Methods/SetTextOperator.md) | None | Sets the text operator for text-based conditional formatting rules. |

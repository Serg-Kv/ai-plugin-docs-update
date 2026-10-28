# ApiUniqueValues

Class representing a unique values conditional formatting rule.

ApiUniqueValues is a subclass of [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| DupeUnique | [XlDuplicateValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDuplicateValues.md) | Returns or sets the setting that specifies whether to format duplicate or unique values for the unique values conditional formatting rule. |
| Type | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the unique values conditional formatting rule. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/Delete.md) | None | Deletes the unique values conditional formatting rule. |
| [GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetAppliesTo.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the range of cells to which the current conditional formatting rule applies. |
| [GetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetDateOperator.md) | [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) \| null | Returns the date operator for time period conditions. |
| [GetDupeUnique](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetDupeUnique.md) | [XlDuplicateValues](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlDuplicateValues.md) | Returns the setting that specifies whether to format duplicate or unique values for the unique values conditional formatting rule. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| null | Returns the fill color for the unique values conditional formatting rule. |
| [GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFont.md) | [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) | Returns the font formatting for the unique values conditional formatting rule. |
| [GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFormula1.md) | string | Returns the first formula used by the current conditional formatting rule. |
| [GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetFormula2.md) | string | Returns the second formula used by the current conditional formatting rule. |
| [GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetNumberFormat.md) | string | Returns the number format for the unique values conditional formatting rule. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetOperator.md) | [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) | Returns the format condition operator. |
| [GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetPTCondition.md) | PTCondition \| null | Returns the pivot table condition object. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetParent.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object of the current format condition. |
| [GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetPriority.md) | number | Returns the priority value of the conditional formatting rule. |
| [GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetScopeType.md) | [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) | Returns the scope type of the conditional formatting rule. |
| [GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetStopIfTrue.md) | boolean | Returns whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetText.md) | string | Returns the text value used in text-based conditional formatting rules. |
| [GetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetTextOperator.md) | [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) \| null | Returns the text operator for text-based conditional formatting rules. |
| [GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/GetType.md) | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the unique values conditional formatting rule. |
| [Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/Modify.md) | [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md) \| null | Modifies the current format condition with the specified parameters. |
| [ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/ModifyAppliesToRange.md) | None | Modifies the cell range to which the current conditional formatting rule applies. |
| [SetBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetBorders.md) | None | Sets the border style for the conditional formatting rule. |
| [SetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetDateOperator.md) | None | Sets the date operator for time period conditions. |
| [SetDupeUnique](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetDupeUnique.md) | None | Sets the setting that specifies whether to format duplicate or unique values for the unique values conditional formatting rule. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetFillColor.md) | None | Sets the fill color for the unique values conditional formatting rule. |
| [SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetFirstPriority.md) | None | Sets the priority value for the current conditional formatting rule to "1" so that it will be evaluated before all other rules on the worksheet. |
| [SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetLastPriority.md) | None | Sets the evaluation order for the current conditional formatting rule so it is evaluated after all other rules on the worksheet. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetNumberFormat.md) | None | Sets the number format for the unique values conditional formatting rule. |
| [SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetPriority.md) | None | Sets the priority value for the conditional formatting rule. |
| [SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetScopeType.md) | None | Sets the scope type for the conditional formatting rule. |
| [SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetStopIfTrue.md) | None | Sets whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetText.md) | None | Sets the text value used in text-based conditional formatting rules. |
| [SetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiUniqueValues/Methods/SetTextOperator.md) | None | Sets the text operator for text-based conditional formatting rules. |

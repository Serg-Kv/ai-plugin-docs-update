# ApiColorScale

Class representing a color scale conditional formatting rule.

ApiColorScale is a subclass of [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md).

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| ColorScaleCriteria | [ApiColorScaleCriterion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion.md)[] | Returns the collection of criteria that define this color scale rule. |
| Type | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the color scale conditional formatting rule. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/Delete.md) | None | Deletes the color scale conditional formatting rule. |
| [GetAppliesTo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetAppliesTo.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the range of cells to which the current conditional formatting rule applies. |
| [GetColorScaleCriteria](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetColorScaleCriteria.md) | [ApiColorScaleCriterion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScaleCriterion.md)[] \| null | Returns the collection of criteria that define this color scale rule. |
| [GetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetDateOperator.md) | [XlTimePeriods](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlTimePeriods.md) \| null | Returns the date operator for time period conditions. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColor.md) \| 'No Fill' | Returns the background color for the format condition. |
| [GetFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetFont.md) | [ApiFont](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFont.md) \| null | Returns the font applied by the current format condition. |
| [GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetFormula1.md) | string | Returns the first formula used by the current conditional formatting rule. |
| [GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetFormula2.md) | string | Returns the second formula used by the current conditional formatting rule. |
| [GetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetNumberFormat.md) | string | Returns the number format applied to a cell when the conditional formatting rule evaluates to true. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetOperator.md) | [XlFormatConditionOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionOperator.md) | Returns the format condition operator. |
| [GetPTCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetPTCondition.md) | PTCondition \| null | Returns the pivot table condition object. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetParent.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object of the current format condition. |
| [GetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetPriority.md) | number | Returns the priority value of the conditional formatting rule. |
| [GetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetScopeType.md) | [XlPivotConditionScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlPivotConditionScope.md) | Returns the scope type of the conditional formatting rule. |
| [GetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetStopIfTrue.md) | boolean | Returns whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. This rule type cannot stop the evaluation, so the value can be changed only by opening a file where it is set. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetText.md) | string | Returns the text value used in text-based conditional formatting rules. |
| [GetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetTextOperator.md) | [XlContainsOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlContainsOperator.md) \| null | Returns the text operator for text-based conditional formatting rules. |
| [GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/GetType.md) | [XlFormatConditionType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/XlFormatConditionType.md) | Returns the type of the color scale conditional formatting rule. |
| [Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/Modify.md) | [ApiFormatCondition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiFormatCondition.md) \| null | Modifies the current format condition with the specified parameters. |
| [ModifyAppliesToRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/ModifyAppliesToRange.md) | None | Modifies the cell range to which the current conditional formatting rule applies. |
| [SetBorders](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetBorders.md) | None | Sets the border style for the conditional formatting rule. |
| [SetDateOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetDateOperator.md) | None | Sets the date operator for time period conditions. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetFillColor.md) | None | Sets the background color to the format condition with the previously created color object. |
| [SetFirstPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetFirstPriority.md) | None | Sets the priority value for the current conditional formatting rule to "1" so that it will be evaluated before all other rules on the worksheet. |
| [SetLastPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetLastPriority.md) | None | Sets the evaluation order for the current conditional formatting rule so it is evaluated after all other rules on the worksheet. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetNumberFormat.md) | None | Sets the number format applied to a cell when the conditional formatting rule evaluates to true. |
| [SetPriority](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetPriority.md) | None | Sets the priority value for the conditional formatting rule. |
| [SetScopeType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetScopeType.md) | None | Sets the scope type for the conditional formatting rule. |
| [SetStopIfTrue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetStopIfTrue.md) | None | Sets whether the editor will stop evaluating additional formatting rules if this rule evaluates to true. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetText.md) | None | Sets the text value used in text-based conditional formatting rules. |
| [SetTextOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiColorScale/Methods/SetTextOperator.md) | None | Sets the text operator for text-based conditional formatting rules. |

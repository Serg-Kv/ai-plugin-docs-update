# ApiValidation

Class representing data validation.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AlertStyle | [ValidationAlertStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationAlertStyle.md) | Returns the validation alert style. |
| ErrorMessage | string | Returns or sets the data validation error message. |
| ErrorTitle | string | Returns or sets the title of the data-validation error dialog box. |
| Formula1 | string | Returns the value or expression associated with the conditional format or data validation. |
| Formula2 | string | Returns the value or expression associated with the second part of a conditional format or data validation. |
| IgnoreBlank | boolean | Returns or sets a Boolean value that specifies whether blank values are permitted by the range data validation. |
| InCellDropdown | boolean | Returns or sets a Boolean value indicating whether data validation displays a drop-down list that contains acceptable values. |
| InputMessage | string | Returns or sets the data validation input message. |
| InputTitle | string | Returns or sets the title of the data-validation input dialog box. |
| Operator | [ValidationOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationOperator.md) | Returns the data validation operator. |
| Parent | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object. |
| ShowError | boolean | Returns or sets a Boolean value indicating whether the data validation error message will be displayed whenever the user enters invalid data. |
| ShowInput | boolean | Returns or sets a Boolean value indicating whether the data validation input message will be displayed whenever the user selects a cell in the data validation range. |
| Type | [ValidationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationType.md) | Returns the validation type. |
| Value | string | Returns the validation value. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Add](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Add.md) | [ApiValidation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation.md) \| null | Adds data validation to the specified range. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Delete.md) | None | Deletes the object. |
| [GetAlertStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetAlertStyle.md) | [ValidationAlertStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationAlertStyle.md) | Returns the validation alert style. |
| [GetErrorMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetErrorMessage.md) | string | Returns the data validation error message. |
| [GetErrorTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetErrorTitle.md) | string | Returns the title of the data-validation error dialog box. |
| [GetFormula1](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetFormula1.md) | string | Returns the first formula in the data validation. |
| [GetFormula2](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetFormula2.md) | string | Returns the second formula in the data validation. |
| [GetIgnoreBlank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetIgnoreBlank.md) | boolean | Returns whether blank values are permitted by the range data validation. |
| [GetInCellDropdown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInCellDropdown.md) | boolean | Returns whether data validation displays a drop-down list that contains acceptable values. |
| [GetInputMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInputMessage.md) | string | Returns the data validation input message. |
| [GetInputTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetInputTitle.md) | string | Returns the title of the data-validation input dialog box. |
| [GetOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetOperator.md) | [ValidationOperator](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationOperator.md) | Returns the data validation operator. |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetParent.md) | [ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiRange.md) | Returns the parent range object. |
| [GetShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetShowError.md) | boolean | Returns whether the data validation error message will be displayed. |
| [GetShowInput](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetShowInput.md) | boolean | Returns whether the data validation input message will be displayed. |
| [GetType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/GetType.md) | [ValidationType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/Enumeration/ValidationType.md) | Returns the validation type. |
| [Modify](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/Modify.md) | [ApiValidation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation.md) \| null | Modifies data validation for a range. |
| [SetErrorMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetErrorMessage.md) | None | Sets the data validation error message. |
| [SetErrorTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetErrorTitle.md) | None | Sets the title of the data-validation error dialog box. |
| [SetIgnoreBlank](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetIgnoreBlank.md) | None | Sets whether blank values are permitted by the range data validation. |
| [SetInCellDropdown](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInCellDropdown.md) | None | Sets whether data validation displays a drop-down list that contains acceptable values. |
| [SetInputMessage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInputMessage.md) | None | Sets the data validation input message. |
| [SetInputTitle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetInputTitle.md) | None | Sets the title of the data-validation input dialog box. |
| [SetShowError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetShowError.md) | None | Sets whether the data validation error message will be displayed. |
| [SetShowInput](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiValidation/Methods/SetShowInput.md) | None | Sets whether the data validation input message will be displayed. |

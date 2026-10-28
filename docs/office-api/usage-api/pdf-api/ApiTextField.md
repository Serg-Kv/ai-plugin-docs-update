# ApiTextField

Class representing a text field.

ApiTextField is a subclass of [ApiBaseField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/AddWidget.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md) \| null \| undefined | Adds new widget - visual representation for field |
| [ClearFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/ClearFormat.md) | boolean | Clears format of field. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/Delete.md) | boolean | Removes field from document. |
| [GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetAllWidgets.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md)[] | Gets array with widgets of the current field. |
| [GetCharLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetCharLimit.md) | number | Gets the text field character limit. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetClassType.md) | "textField" | Returns a type of the ApiTextField class. |
| [GetFormattedValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetFormattedValue.md) | string | Gets formatted value of a field. |
| [GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetFullName.md) | string | Gets field full name. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetInternalId.md) | string | Returns an internal ID of the current field. |
| [GetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetPartialName.md) | string | Gets field partial name. |
| [GetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetPlaceholder.md) | string | Gets text field placeholder. |
| [GetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetRegularExp.md) | boolean | Gets text widget regular validate expression. |
| [GetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetTooltip.md) | boolean | Gets field tooltip |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/GetValue.md) | string \| string[] | Gets field value |
| [IsComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsComb.md) | boolean | Checks if the text field uses comb formatting. |
| [IsMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsMultiline.md) | boolean | Checks if text field is multiline. |
| [IsReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsReadOnly.md) | boolean | Checks if field is read only |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsRequired.md) | boolean | Checks if field is required |
| [IsScrollLongText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/IsScrollLongText.md) | boolean | Checks if text field can scroll long text. |
| [SetCharLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetCharLimit.md) | boolean | Sets the text field character limit. |
| [SetComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetComb.md) | boolean | Sets whether the text field uses comb formatting. |
| [SetDateFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetDateFormat.md) | boolean | Sets date format for field. |
| [SetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetFullName.md) | boolean | Sets new field name if possible. |
| [SetMask](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetMask.md) | boolean | Sets the input mask for entered text. |
| [SetMultiline](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetMultiline.md) | boolean | Sets text field multiline prop. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetNumberFormat.md) | boolean | Sets number format for field. |
| [SetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetPartialName.md) | boolean | Sets new field partial name. |
| [SetPercentageFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetPercentageFormat.md) | boolean | Sets percentage format for field. |
| [SetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetPlaceholder.md) | boolean | Sets text field placeholder. |
| [SetReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetReadOnly.md) | boolean | Sets field read only |
| [SetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetRegularExp.md) | boolean | Sets regular expression validate string for field. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetRequired.md) | boolean | Sets field required |
| [SetScrollLongText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetScrollLongText.md) | boolean | Sets whether the text field can scroll long text. |
| [SetSpecialFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetSpecialFormat.md) | boolean | Sets special format for field. |
| [SetTimeFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetTimeFormat.md) | boolean | Sets time format for field. |
| [SetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetTooltip.md) | boolean | Sets field tooltip |
| [SetValidateRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetValidateRange.md) | boolean | Sets validate range for field. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField/Methods/SetValue.md) | boolean | Sets field value |

# ApiComboboxField

Class representing a combobox field.

ApiComboboxField is a subclass of [ApiBaseListField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/AddOption.md) | boolean | Adds new option to list options. |
| [AddWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/AddWidget.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md) \| null \| undefined | Adds new widget - visual representation for field |
| [ClearFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/ClearFormat.md) | boolean | Clears format of field. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/Delete.md) | boolean | Removes field from document. |
| [GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetAllWidgets.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md)[] | Gets array with widgets of the current field. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetClassType.md) | "comboboxField" | Returns a type of the ApiComboboxField class. |
| [GetFormattedValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetFormattedValue.md) | string | Gets formatted value of a field. |
| [GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetFullName.md) | string | Gets field full name. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetInternalId.md) | string | Returns an internal ID of the current field. |
| [GetOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetOption.md) | [ListOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ListOption.md) | Gets option from list options. |
| [GetOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetOptions.md) | [ListOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ListOption.md)[] | Gets all options from list options. |
| [GetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetPartialName.md) | string | Gets field partial name. |
| [GetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetPlaceholder.md) | string | Gets text field placeholder. |
| [GetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetRegularExp.md) | boolean | Gets text widget regular validate expression. |
| [GetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetTooltip.md) | boolean | Gets field tooltip |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetValue.md) | string \| string[] | Gets field value |
| [GetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/GetValueIndexes.md) | number[] | Gets selected value indexes. |
| [IsCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsCommitOnSelChange.md) | boolean | Checks if field can commit on selection change. |
| [IsEditable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsEditable.md) | boolean | Checks if field is editable. |
| [IsReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsReadOnly.md) | boolean | Checks if field is read only |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/IsRequired.md) | boolean | Checks if field is required |
| [MoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/MoveOption.md) | boolean | Moves option to specified position in list options. |
| [RemoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/RemoveOption.md) | boolean | Removes option from list options. |
| [SetCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetCommitOnSelChange.md) | boolean | Sets whether the field commits changes immediately after selection changes. |
| [SetDateFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetDateFormat.md) | boolean | Sets date format for field. |
| [SetEditable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetEditable.md) | boolean | Sets whether custom text can be entered. |
| [SetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetFullName.md) | boolean | Sets new field name if possible. |
| [SetMask](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetMask.md) | boolean | Sets mask for field. |
| [SetNumberFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetNumberFormat.md) | boolean | Sets number format for field. |
| [SetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetPartialName.md) | boolean | Sets new field partial name. |
| [SetPercentageFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetPercentageFormat.md) | boolean | Sets percentage format for field. |
| [SetPlaceholder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetPlaceholder.md) | boolean | Sets text field placeholder. |
| [SetReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetReadOnly.md) | boolean | Sets field read only |
| [SetRegularExp](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetRegularExp.md) | boolean | Sets regular expression validate string for field. |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetRequired.md) | boolean | Sets field required |
| [SetSpecialFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetSpecialFormat.md) | boolean | Sets special format for field. |
| [SetTimeFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetTimeFormat.md) | boolean | Sets time format for field. |
| [SetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetTooltip.md) | boolean | Sets field tooltip |
| [SetValidateRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetValidateRange.md) | boolean | Sets validate range for field. |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetValue.md) | boolean | Sets field value |
| [SetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField/Methods/SetValueIndexes.md) | boolean | Sets selected value indexes. |

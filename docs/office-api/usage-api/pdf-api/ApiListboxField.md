# ApiListboxField

Class representing a listbox field.

ApiListboxField is a subclass of [ApiBaseListField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseListField.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/AddOption.md) | boolean | Adds new option to list options. |
| [AddWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/AddWidget.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md) \| null \| undefined | Adds new widget - visual representation for field |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/Delete.md) | boolean | Removes field from document. |
| [GetAllWidgets](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetAllWidgets.md) | [ApiWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiWidget.md)[] | Gets array with widgets of the current field. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetClassType.md) | "listboxField" | Returns a type of the ApiListboxField class. |
| [GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetFullName.md) | string | Gets field full name. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetInternalId.md) | string | Returns an internal ID of the current field. |
| [GetOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetOption.md) | [ListOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ListOption.md) | Gets option from list options. |
| [GetOptions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetOptions.md) | [ListOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ListOption.md)[] | Gets all options from list options. |
| [GetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetPartialName.md) | string | Gets field partial name. |
| [GetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetTooltip.md) | boolean | Gets field tooltip |
| [GetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetValue.md) | string \| string[] | Gets field value |
| [GetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/GetValueIndexes.md) | number[] | Gets selected value indexes. |
| [IsCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsCommitOnSelChange.md) | boolean | Checks if field can commit on selection change. |
| [IsMultipleSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsMultipleSelection.md) | boolean | Checks if the field supports multiple selection. |
| [IsReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsReadOnly.md) | boolean | Checks if field is read only |
| [IsRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/IsRequired.md) | boolean | Checks if field is required |
| [MoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/MoveOption.md) | boolean | Moves option to specified position in list options. |
| [RemoveOption](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/RemoveOption.md) | boolean | Removes option from list options. |
| [SetCommitOnSelChange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetCommitOnSelChange.md) | boolean | Sets whether the field commits changes immediately after selection changes. |
| [SetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetFullName.md) | boolean | Sets new field name if possible. |
| [SetMultipleSelection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetMultipleSelection.md) | boolean | Sets whether multiple values can be selected. |
| [SetPartialName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetPartialName.md) | boolean | Sets new field partial name. |
| [SetReadOnly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetReadOnly.md) | boolean | Sets field read only |
| [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetRequired.md) | boolean | Sets field required |
| [SetTooltip](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetTooltip.md) | boolean | Sets field tooltip |
| [SetValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetValue.md) | boolean | Sets field value |
| [SetValueIndexes](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField/Methods/SetValueIndexes.md) | boolean | Sets selected value indexes. |

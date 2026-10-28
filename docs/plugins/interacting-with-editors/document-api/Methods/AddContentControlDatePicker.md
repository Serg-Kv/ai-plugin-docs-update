# AddContentControlDatePicker

Adds an empty content control datepicker to the document.

## Syntax

```javascript
expression.AddContentControlDatePicker(datePickerPr, commonPr);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| datePickerPr | Optional | [ContentControlDatePickerProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControlDatePickerProperties.md) | \{\} | The content control datepicker properties. |
| commonPr | Optional | [ContentControlProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControlProperties.md) | \{\} | The common content control properties. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("AddContentControlDatePicker", [
    {
        "DateFormat" : "DD\ MMMM\ YYYY",
        "Date" : new window.Date()
    },
    {
        "Id" : 7,
        "Tag" : "{tag}",
        "Lock" : 0
    }
]);
```

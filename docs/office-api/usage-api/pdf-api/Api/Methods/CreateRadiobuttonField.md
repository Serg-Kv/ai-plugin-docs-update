# CreateRadiobuttonField

Creates a radiobutton field.

## Syntax

```javascript
expression.CreateRadiobuttonField(rect);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| rect | Required | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) |  | widget rect |

## Returns

[ApiRadiobuttonField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField.md)

## Example

Add a radio button field to a PDF form.

```javascript editor-pdf
// How do I create a group of selectable radio buttons in a PDF?

// Create a radio button field and configure options in a PDF.

let doc = Api.GetDocument();
let page = doc.GetPage(0);

let radioField = Api.CreateRadiobuttonField([10, 10, 25, 25]);
page.AddObject(radioField);
radioField.AddOption(0, [10, 30, 25, 45], 'Choice 2');
radioField.SetValue('Choice 2');
```

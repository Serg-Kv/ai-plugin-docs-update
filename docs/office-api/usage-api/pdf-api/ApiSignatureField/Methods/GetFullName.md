# GetFullName

Gets field full name.

Inherited from [ApiBaseField.GetFullName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseField/Methods/GetFullName.md).

## Syntax

```javascript
expression.GetFullName();
```

`expression` - A variable that represents an [ApiSignatureField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

string

## Example

Read the complete name identifier of a form field in a PDF.

```javascript editor-pdf
// How do I retrieve the full name assigned to a form field in a PDF?

// Display the unique full name property of a form field in a PDF.

let doc = Api.GetDocument();
let page = doc.GetPage(0);
let textField = Api.CreateTextField([10, 10, 160, 30]);
page.AddObject(textField);

textField.SetValue('Field full name is: ' + textField.GetFullName());
```

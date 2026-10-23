# CreateDateForm

Creates a date form with the specified date form properties.

## Syntax

```javascript
expression.CreateDateForm(formPr);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| formPr | Required | [DateFormPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/DateFormPr.md) |  | Date form properties. |

## Returns

[ApiDateForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm.md)

## Example

Create a date entry field where users input calendar dates in a document.

```javascript editor-forms
// How do I add a date picker field to a document?

// Set up a form field that accepts date values with specific formatting in a document.

let doc = Api.GetDocument();
let dateForm = Api.CreateDateForm({
	"key": "Nowadays",
	"tip": "Enter current date",
	"required": true,
	"placeholder": "Your date here",
	"format": "mm.dd.yyyy",
	"lang": "en-US"
});
let paragraph = doc.GetElement(0);
paragraph.AddElement(dateForm);
```

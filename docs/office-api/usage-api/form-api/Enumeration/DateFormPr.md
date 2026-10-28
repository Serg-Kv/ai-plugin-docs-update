# DateFormPr

The date form properties.

## Type

Enumeration

## Values

- [FormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormPrBase.md)
- [DateFormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/DateFormPrBase.md)

## Example

Create a date form with the common and specific date form properties.

```javascript editor-forms
// How do I create a date form with its properties?

// Create the properties and apply them to the ApiDateForm object.

let dateFormPr = {
	"key": "Nowadays",
	"tip": "Enter current date",
	"required": true,
	"placeholder": "Your date here",
	"format": "mm.dd.yyyy",
	"lang": "en-US"
};
let dateForm = Api.CreateDateForm(dateFormPr);
```

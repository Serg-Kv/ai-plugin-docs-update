# TextFormInsertPr

Properties for inserting a text field.

## Type

Enumeration

## Values

- [FormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormPrBase.md)
- [TextFormPrBase](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/TextFormPrBase.md)
- [FormInsertPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/FormInsertPr.md)

## Example

Insert a text box with the specified text box properties over the selected text.

```javascript editor-forms
// How do I insert a text form with properties such as a tip and a placeholder?

// Add a text form with properties.

let textFormInsertPr = {
	"key": "Personal information",
	"tip": "Enter your first name",
	"required": true,
	"placeholder": "Name",
	"comb": true,
	"maxCharacters": 10,
	"cellWidth": 3,
	"multiLine": false,
	"autoFit": false,
	"placeholderFromSelection": true,
	"keepSelectedTextInForm": false
};
doc.InsertTextForm(textFormInsertPr);
```

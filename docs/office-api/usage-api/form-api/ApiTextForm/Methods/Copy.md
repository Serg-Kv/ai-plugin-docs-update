# Copy

Copies the current form (copies with the shape if it exists).

Inherited from [ApiFormBase.Copy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/Copy.md).

## Syntax

```javascript
expression.Copy();
```

`expression` - A variable that represents an [ApiTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Enumeration/ApiForm.md) \| null \| undefined

## Example

Duplicate a text input field and place the copy in a document.

```javascript editor-forms
// How do I create an identical second text field from an existing one in a document?

// Reproduce a text entry field so it can be reused elsewhere in a document.

let doc = Api.GetDocument();
let textForm = Api.CreateTextForm({"key": "Personal information", "tip": "Enter your first name", "required": true, "placeholder": "First name", "comb": true, "maxCharacters": 10, "cellWidth": 3, "multiLine": false, "autoFit": false});
let paragraph = doc.GetElement(0);
paragraph.AddElement(textForm);
let copyTextForm = textForm.Copy();
paragraph.AddLineBreak();
paragraph.AddElement(copyTextForm);
```

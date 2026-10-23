# Add

Appends the text content of the given form to the end of the current complex form.

## Syntax

```javascript
expression.Add(value);
```

`expression` - A variable that represents an [ApiComplexForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComplexForm.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| value | Required | string \| [ApiDateForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDateForm.md) \| [ApiPictureForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiPictureForm.md) \| [ApiCheckBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiCheckBoxForm.md) \| [ApiComboBoxForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComboBoxForm.md) \| [ApiTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm.md) |  | The text or the form to add. |

## Returns

boolean

## Example

Add elements to a complex form in a document.

```javascript editor-docx
// How do I add form fields and static text to a complex form in a document?

// Build a multi-part entry field by combining a text input and a suffix label inside one form.

let doc = Api.GetDocument();
let complexForm = Api.CreateComplexForm({"key": "Email", "tip": "Email", "placeholder": "Start to fill complex form"});
complexForm.Add(Api.CreateTextForm());
complexForm.Add("@onlyoffice.com");
let paragraph = doc.GetElement(0);
paragraph.AddElement(complexForm);
```

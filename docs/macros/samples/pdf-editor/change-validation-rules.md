---
hide_table_of_contents: true
description: Change validation rules for phone and email form fields.
tags: ["Docs", "Macros", "PDF"]
---

import Video from '@site/src/components/Video/Video';

# Change validation rules

Changes the validation rules of the number and email fields in the document.

```ts
(function () {
    let doc = Api.GetDocument();
    let forms = doc.GetAllForms();

    forms.forEach((form) => {
        if (form.GetFormType() === "textForm") {
            let formKey = form.GetFormKey();
            let formText = form.GetText();

            if (/^\(\d{3}\)\d{3}-\d{4}$/.test(formText)) {
                form.SetCharactersLimit(14);
                form.SetRequired(true);
                form.SetPlaceholderText("(123)456-7890");
                form.SetComb(true);
            } else if (
                /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/.test(formText)
            ) {
                form.SetCharactersLimit(254);
                form.SetRequired(true);
                form.SetPlaceholderText("example@example.com");
            }
        }
    });
})();
```

Methods used: [GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetDocument.md), [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetAllForms.md), [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetFormType.md), [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetFormKey.md), [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/GetText.md), [SetCharactersLimit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetCharactersLimit.md), [SetRequired](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetRequired.md), [SetPlaceholderText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetPlaceholderText.md), [SetComb](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiTextForm/Methods/SetComb.md)

## Result

<Video src="https://api.onlyoffice.com/assets/video/macros/pdf-editor/change-validation-rules" dark />

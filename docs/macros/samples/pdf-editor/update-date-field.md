---
hide_table_of_contents: true
description: Set the current date in all date form fields.
tags: ["Docs", "Macros", "PDF"]
---

import Video from '@site/src/components/Video/Video';

# Update date field

Sets the current date to all date form fields in the document.

```ts
(function () {
  let doc = Api.GetDocument();
  let forms = doc.GetAllForms();

  forms.forEach((form) => {
    if (form.GetFormType() === "dateForm") {
      form.SetFormat("dddd, dd MMMM yyyy");
      form.SetLanguage("en-CA");

      form.SetBackgroundColor(255, 0, 0); // Set background color to red.
    }
  });
})();
```

Methods used: [GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetDocument.md), [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDocument/Methods/GetAllForms.md), [GetFormType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiFormBase/Methods/GetFormType.md), [SetFormat](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/SetFormat.md), [SetLanguage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/SetLanguage.md), [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/ApiDateForm/Methods/SetBackgroundColor.md)

## Result

<Video src="https://api.onlyoffice.com/assets/video/macros/pdf-editor/update-date-field" dark />

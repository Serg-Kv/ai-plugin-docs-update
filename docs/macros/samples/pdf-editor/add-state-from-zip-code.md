---
hide_table_of_contents: true
description: Auto-fill the state field based on the entered zip code.
tags: ["Docs", "Macros", "PDF"]
---

import Video from '@site/src/components/Video/Video';

# Add state from zip code

Adds the "State" label and the text form prefilled with "CA" if the zip code of California is entered. It can be extended by using API to prefill "State" when entering the zip code.

```ts
(function()
{
    let doc = Api.GetDocument();
    let allForms = doc.GetAllForms();
    //California Zip Codes regex
    let zipRegex = /^9[0-5][0-9]{3}$/;
    
    allForms.forEach(form => {
        if(form.GetFormKey() == "ZipCode") {
            let input = form.GetText();
            //If the zip code is Californian, add the "State" label with the text form indicating "CA"
            if(zipRegex.test(input)) {
                let stateForm = allForms.find(item => item.GetFormKey() === "State");
                if(stateForm == null) {
                    let stateTextForm = Api.CreateTextForm({"key": "State", "tip": "State", "required": false, "placeholder": "State", "comb": true, "maxCharacters": 2, "cellWidth": 3, "multiLine": false, "autoFit": false});
                    stateTextForm.SetText("CA");
                    let paragraph = Api.CreateParagraph();
                    paragraph.AddTabStop();
                    paragraph.AddText("State: ");
                    paragraph.AddElement(stateTextForm);
                    doc.InsertContent([paragraph]);
                }
                else {
                    stateForm.SetText("CA");
                }
            }
        }
    });
})();
```

Methods used: [GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetDocument.md), [GetAllForms](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetAllForms.md), [GetFormKey](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetFormKey.md), [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiFormBase/Methods/GetText.md), [CreateTextForm](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/form-api/Api/Methods/CreateTextForm.md), [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTextForm/Methods/SetText.md), [CreateParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/CreateParagraph.md), [AddTabStop](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddTabStop.md), [AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddText.md), [AddElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddElement.md), [InsertContent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/InsertContent.md)

## Result

<Video src="https://api.onlyoffice.com/assets/video/macros/pdf-editor/add-state-from-zip-code" dark />

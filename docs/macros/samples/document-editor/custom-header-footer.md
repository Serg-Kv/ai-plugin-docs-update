---
hide_table_of_contents: true
description: Generate custom headers and footers for a document.
tags: ["Docs", "Macros", "Documents"]
---

import Video from '@site/src/components/Video/Video';

# Custom header and footer

Applies predefined headers and footers to all pages in the document.

```ts
(function () {
    let doc = Api.GetDocument();
    let sections = doc.GetSections();

    for (let section of sections) {
        // Remove existing headers and footers
        section.RemoveHeader("default");
        section.RemoveFooter("default");

        // Create new header and footer
        let header = section.GetHeader("default", true);
        let footer = section.GetFooter("default", true);

        // Set header content
        let headerPara = header.GetElement(0);
        headerPara.AddText("Your Header Text");
        headerPara.SetJc("center");

        // Set footer content
        let footerPara = footer.GetElement(0);
        footerPara.AddText("Your Footer Text - Page ");
        footerPara.AddPageNumber();
        footerPara.SetJc("center");
    }

    return true;
})();
```

Methods used: [GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetDocument.md), [GetSections](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetSections.md), [RemoveHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/RemoveHeader.md), [RemoveFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/RemoveFooter.md), [GetHeader](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetHeader.md), [GetFooter](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiSection/Methods/GetFooter.md), [GetElement](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocumentContent/Methods/GetElement.md), [AddText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddText.md), [SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetJc.md), [AddPageNumber](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddPageNumber.md)

## Result

<Video src="https://api.onlyoffice.com/assets/video/macros/document-editor/custom-header-footer" dark />

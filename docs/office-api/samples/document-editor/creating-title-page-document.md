---
hide_table_of_contents: true
description: Create a formatted title page with centered text.
tags: ["Docs", "Office API", "Documents"]
---

# Creating title page document

Create a document with a formatted title page featuring centered text and proper spacing:

- create a title page with centered alignment and custom spacing ([Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api.md), [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md));
- format the title with large font size and top margin ([ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md), [ApiParagraph/SetJc](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetJc.md));
- add author and date information with proper spacing ([ApiParagraph/SetSpacingBefore](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/SetSpacingBefore.md));
- insert a page break to separate title page from content ([ApiParagraph/AddPageBreak](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph/Methods/AddPageBreak.md)).

```ts editor-docx zoom=60
let doc = Api.GetDocument();

// Sample data for the title page
let titleData = {
  title: "Annual Business Report",
  author: "Emily Johnson",
  date: "June 2025"
};

// Create title paragraph
let titleParagraph = doc.GetElement(0);
titleParagraph.SetJc("center");
titleParagraph.SetSpacingBefore(5760); // 80pt top margin (72 points = 1 inch)
let titleRun = titleParagraph.AddText(titleData.title);
titleRun.SetFontSize(36); // 18pt font size (doubled for API)
titleRun.SetBold(true);

// Create author paragraph
let authorParagraph = Api.CreateParagraph();
authorParagraph.SetJc("center");
authorParagraph.SetSpacingBefore(2880); // 40pt spacing
let authorRun = authorParagraph.AddText("Author: " + titleData.author);
authorRun.SetFontSize(24); // 12pt font size
doc.Push(authorParagraph);

// Create date paragraph
let dateParagraph = Api.CreateParagraph();
dateParagraph.SetJc("center");
dateParagraph.SetSpacingBefore(1440); // 20pt spacing
let dateRun = dateParagraph.AddText(titleData.date);
dateRun.SetFontSize(22); // 11pt font size
doc.Push(dateParagraph);

// Add page break to start content on new page
let pageBreakParagraph = Api.CreateParagraph();
pageBreakParagraph.AddPageBreak();
doc.Push(pageBreakParagraph);

// Add sample content on the new page
let contentParagraph = Api.CreateParagraph();
let headingRun = contentParagraph.AddText("1. Executive Summary");
headingRun.SetBold(true);
headingRun.SetFontSize(28); // 14pt font size
doc.Push(contentParagraph);

let bodyParagraph = Api.CreateParagraph();
bodyParagraph.SetSpacingBefore(720); // 10pt spacing
bodyParagraph.AddText("This report presents the annual business performance, key financials, strategic highlights, and recommendations for the next fiscal year. The document provides comprehensive analysis of market trends, operational efficiency, and growth opportunities that will guide our strategic direction moving forward.");
doc.Push(bodyParagraph);

// Add another section
let section2Paragraph = Api.CreateParagraph();
section2Paragraph.SetSpacingBefore(1440); // 20pt spacing
let section2Run = section2Paragraph.AddText("2. Financial Overview");
section2Run.SetBold(true);
section2Run.SetFontSize(28); // 14pt font size
doc.Push(section2Paragraph);

let financial2Paragraph = Api.CreateParagraph();
financial2Paragraph.SetSpacingBefore(720); // 10pt spacing
financial2Paragraph.AddText("The financial performance for this fiscal year demonstrates strong growth across all key metrics. Revenue increased by 15% compared to the previous year, while operational costs were optimized through strategic initiatives and process improvements.");
doc.Push(financial2Paragraph);
```

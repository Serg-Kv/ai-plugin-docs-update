---
sidebar_position: -1
---

# PDF API

A PDF document is organized as a sequence of *pages*. Each page can contain several types of content: paragraphs, tables, drawings (images, shapes, charts), annotations, and interactive form fields.

The core content elements are:

- *Paragraph* ([`ApiParagraph`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParagraph.md)) — a block of text. Paragraphs consist of one or more *runs* ([`ApiRun`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRun.md)), each of which carries the text itself and its character formatting (font, size, bold, italic, color, etc.).
- *Table* ([`ApiTable`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTable.md)) — a grid structure whose cells ([`ApiTableCell`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTableCell.md)) contain document content (paragraphs).
- *Drawing* ([`ApiDrawing`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDrawing.md)) — an image, shape, or chart placed at a specific position on the page.

Pages and their content are accessed through the *document* ([`ApiDocument`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiDocument.md)) and *page* ([`ApiPage`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPage.md)) objects.

### Annotations

Annotations let you mark up PDF content without modifying it. The PDF API supports the following annotation types:

| Category | Types |
|---|---|
| Note/text | [`ApiTextAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation.md), [`ApiFreeTextAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiFreeTextAnnotation.md) |
| Markup | [`ApiHighlightAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation.md), [`ApiUnderlineAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiUnderlineAnnotation.md), [`ApiStrikeoutAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStrikeoutAnnotation.md), [`ApiCaretAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCaretAnnotation.md) |
| Shapes | [`ApiSquareAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSquareAnnotation.md), [`ApiCircleAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCircleAnnotation.md), [`ApiLineAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiLineAnnotation.md), [`ApiPolyLineAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolyLineAnnotation.md), [`ApiPolygonAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation.md) |
| Other | [`ApiInkAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiInkAnnotation.md), [`ApiStampAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiStampAnnotation.md), [`ApiRedactAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRedactAnnotation.md) |

All annotation types share a common base ([`ApiBaseAnnotation`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation.md)) that provides border, fill, opacity, author, date, and reply properties.

### Form fields and widgets

PDF forms include *fields* and *widgets*. A field defines the data model (name, value, validation rules), while a widget determines the visual representation of a field.

| Field type | Widget |
|---|---|
| [`ApiTextField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField.md) | [`ApiBaseWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md) |
| [`ApiComboboxField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiComboboxField.md) | [`ApiBaseWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md) |
| [`ApiListboxField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiListboxField.md) | [`ApiBaseWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md) |
| [`ApiCheckboxField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxField.md) | [`ApiCheckboxWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget.md) |
| [`ApiRadiobuttonField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiRadiobuttonField.md) | [`ApiCheckboxWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiCheckboxWidget.md) |
| [`ApiButtonField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonField.md) | [`ApiButtonWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget.md) |
| [`ApiSignatureField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiSignatureField.md) | [`ApiBaseWidget`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md) |

Date fields created with [`Api.CreateDateField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateDateField.md) are [`ApiTextField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextField.md) objects, and image fields created with [`Api.CreateImageField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateImageField.md) are [`ApiButtonField`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonField.md) objects.

## Creating a new PDF document

To create a PDF document with **ONLYOFFICE Document Builder**, you first create a document in an editable format (DOCX) and then save it as PDF. The simplest example creates a single page with centered "Center" text:

```ts
// create a document file with ONLYOFFICE Document Builder
builder.CreateFile("docx");

// create a new 'oDocument' variable and get the created document
const oDocument = Api.GetDocument();

// create a new paragraph for the document content
const oParagraph = Api.CreateParagraph();

// set the paragraph justification to center the text
oParagraph.SetJc("center");

// add a text containing a single 'Center' word to the paragraph
oParagraph.AddText("Center");

// push the paragraph to the document
oDocument.Push(oParagraph);

// save the resulting document as a PDF file with the 'example.pdf' name and close it
builder.SaveFile("pdf", "example.pdf");
builder.CloseFile();
```

The document initializes with a default page configuration. You can customize page size, orientation, and margins using the appropriate page configuration methods.

## Opening an existing PDF document

To edit an existing PDF document, open it with `builder.OpenFile`, then get its pages and modify their content:

```ts
// use a path or URL to an existing 'mydocument.pdf' file to open it with ONLYOFFICE Document Builder
builder.OpenFile("https://example.com/mydocument.pdf");

// create a new 'oDocument' variable and get the opened PDF document contents
const oDocument = Api.GetDocument();

// get the first page
const oPage = oDocument.GetElement(0);

// create and configure a new paragraph
const oParagraph = Api.CreateParagraph();
oParagraph.SetJc("center");
oParagraph.AddText("Center");

// add the paragraph to the page
oPage.Push(oParagraph);

// save the resulting PDF document as a file in the .pdf format with a new 'example.pdf' name and close it
builder.SaveFile("pdf", "example.pdf");
builder.CloseFile();
```

Use the appropriate API documentation sections to find out which methods allow you to change certain PDF document element formatting properties and work with PDF-specific features.

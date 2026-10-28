# GetIndRight

Returns the paragraph right side indentation.

Inherited from [ApiParaPr.GetIndRight](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParaPr/Methods/GetIndRight.md).

## Syntax

```javascript
expression.GetIndRight();
```

`expression` - A variable that represents an [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[twips](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/twips.md) \| undefined

## Example

Read the right indentation value set on a paragraph in a document.

```javascript editor-docx
// How do I find out how much a paragraph is indented from the right margin in a document?

// Confirm a programmatically applied right indent by reading it back in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is a paragraph with the right offset of 2 inches set to it. ");
paragraph.AddText("These sentences are used to add lines for demonstrative purposes. ");
paragraph.AddText("These sentences are used to add lines for demonstrative purposes. ");
paragraph.AddText("These sentences are used to add lines for demonstrative purposes.");
paragraph.SetJc("right");
paragraph.SetIndRight(2880);
let indRight = paragraph.GetIndRight();
paragraph = Api.CreateParagraph();
paragraph.AddText("Right indent: " + indRight);
doc.Push(paragraph);
```

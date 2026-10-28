# GetRange

Returns a Range object that represents the part of the document contained in the specified document.

## Syntax

```javascript
expression.GetRange(Start, End);
```

`expression` - A variable that represents an [ApiDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Start | Required | Number |  | Start position index in the current element. |
| End | Required | Number |  | End position index in the current element. |

## Returns

[ApiRange](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange.md)

## Example

Select a specific text range by character positions in a document.

```javascript editor-docx
// How do I get a range of characters using start and end indexes in a document?

// Apply bold formatting to a precise word by targeting it with index-based range selection in a document.

let doc = Api.GetDocument();
let paragraph = doc.GetElement(0);
paragraph.AddText("This is just a sample text.");
let range = doc.GetRange(8, 11);
range.SetBold(true);
```

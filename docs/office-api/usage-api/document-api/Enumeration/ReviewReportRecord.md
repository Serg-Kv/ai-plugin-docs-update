# ReviewReportRecord

Represents a single review change record.

## Type

Object

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| Date | number | The timestamp of the change. |
| ReviewedElement | [ApiParagraph](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiParagraph.md) \| [ApiTable](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiTable.md) | The element that was reviewed. |
| Type | [ReviewReportRecordType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Enumeration/ReviewReportRecordType.md) | The review record type. |
| Value | string | The review change value (only for "TextAdd" and "TextRem" types). |

# ApiHighlightAnnotation

Class representing a highlight annotation.

ApiHighlightAnnotation is a subclass of [ApiBaseMarkupAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseMarkupAnnotation.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/AddReply.md) | boolean | Adds reply on this annot. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/Delete.md) | boolean | Removes annotation from document. |
| [GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetAuthorName.md) | string | Gets annotation author name. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets annotation border color. |
| [GetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetBorderEffectIntensity.md) | number | Gets annotation border effect intensity. |
| [GetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetBorderEffectStyle.md) | [AnnotBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/AnnotBorderEffectStyle.md) | Gets annotation border effect style. |
| [GetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetBorderStyle.md) | [AnnotBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/AnnotBorderStyle.md) | Gets annotation border style. |
| [GetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetBorderWidth.md) | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/pt.md) | Gets annotation border width. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetClassType.md) | "highlightAnnot" | Returns a type of the ApiHighlightAnnotation class. |
| [GetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetContents.md) | string \| null \| undefined | Gets annotation contents. |
| [GetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetCreationDate.md) | number | Gets annotation creation date. |
| [GetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetDashPattern.md) | number[] | Gets annotation dash pattern. |
| [GetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetDisplay.md) | [DisplayType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DisplayType.md) | Gets annotation display type. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets annotation fill color. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetInternalId.md) | string | Returns an internal ID of the current annotation. |
| [GetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetModDate.md) | number | Gets annotation last modification date. |
| [GetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetOpacity.md) | string | Gets annotation opacity. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetPosition.md) | [Point](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Point.md) | Gets annotation position. |
| [GetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetQuads.md) | [Quad](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Quad.md)[] | Gets quads from current markup annotation. |
| [GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetRect.md) | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) | Gets annotation rect. |
| [GetReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetReplies.md) | [ApiTextAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation.md)[] | Gets replies on this annot. |
| [GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetSubject.md) | string \| null \| undefined | Gets annotation subject. |
| [GetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/GetUniqueName.md) | string | Gets annotation unique name. |
| [SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetAuthorName.md) | boolean | Sets annotation author name. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetBorderColor.md) | boolean | Sets annotation border color. |
| [SetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetBorderEffectIntensity.md) | boolean | Sets annotation border effect intensity. |
| [SetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetBorderEffectStyle.md) | boolean | Sets annotation border effect style. |
| [SetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetBorderStyle.md) | boolean | Sets annotation border style. |
| [SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetBorderWidth.md) | boolean | Sets annotation border width. |
| [SetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetContents.md) | boolean | Sets annotation contents. |
| [SetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetCreationDate.md) | boolean | Sets annotation creation date. |
| [SetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetDashPattern.md) | boolean | Sets annotation dash pattern. |
| [SetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetDisplay.md) | boolean | Sets annotation display type. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetFillColor.md) | boolean | Sets annotation fill color. |
| [SetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetModDate.md) | boolean | Sets annotation last modification date. |
| [SetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetOpacity.md) | boolean | Sets annotation opacity. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetPosition.md) | boolean | Sets annotation position. |
| [SetQuads](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetQuads.md) | boolean | Sets quads to current markup annotation. |
| [SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetRect.md) | boolean | Sets annotation rect. |
| [SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetSubject.md) | boolean | Sets annotation subject. |
| [SetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiHighlightAnnotation/Methods/SetUniqueName.md) | boolean | Sets annotation unique name. |

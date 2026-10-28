# ApiPolygonAnnotation

Class representing a polygon annotation.

ApiPolygonAnnotation is a subclass of [ApiBaseAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseAnnotation.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/AddReply.md) | boolean | Adds reply on this annot. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/Delete.md) | boolean | Removes annotation from document. |
| [GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetAuthorName.md) | string | Gets annotation author name. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets annotation border color. |
| [GetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetBorderEffectIntensity.md) | number | Gets annotation border effect intensity. |
| [GetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetBorderEffectStyle.md) | [AnnotBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/AnnotBorderEffectStyle.md) | Gets annotation border effect style. |
| [GetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetBorderStyle.md) | [AnnotBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/AnnotBorderStyle.md) | Gets annotation border style. |
| [GetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetBorderWidth.md) | [pt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/pt.md) | Gets annotation border width. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetClassType.md) | "polygonAnnot" | Returns a type of the ApiPolygonAnnotation class. |
| [GetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetContents.md) | string \| null \| undefined | Gets annotation contents. |
| [GetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetCreationDate.md) | number | Gets annotation creation date. |
| [GetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetDashPattern.md) | number[] | Gets annotation dash pattern. |
| [GetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetDisplay.md) | [DisplayType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/DisplayType.md) | Gets annotation display type. |
| [GetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetFillColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets annotation fill color. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetInternalId.md) | string | Returns an internal ID of the current annotation. |
| [GetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetModDate.md) | number | Gets annotation last modification date. |
| [GetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetOpacity.md) | string | Gets annotation opacity. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetPosition.md) | [Point](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Point.md) | Gets annotation position. |
| [GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetRect.md) | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) | Gets annotation rect. |
| [GetReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetReplies.md) | [ApiTextAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiTextAnnotation.md)[] | Gets replies on this annot. |
| [GetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetSubject.md) | string \| null \| undefined | Gets annotation subject. |
| [GetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetUniqueName.md) | string | Gets annotation unique name. |
| [GetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/GetVertices.md) | [Path](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Path.md) | Gets ink path list. |
| [SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetAuthorName.md) | boolean | Sets annotation author name. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetBorderColor.md) | boolean | Sets annotation border color. |
| [SetBorderEffectIntensity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetBorderEffectIntensity.md) | boolean | Sets annotation border effect intensity. |
| [SetBorderEffectStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetBorderEffectStyle.md) | boolean | Sets annotation border effect style. |
| [SetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetBorderStyle.md) | boolean | Sets annotation border style. |
| [SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetBorderWidth.md) | boolean | Sets annotation border width. |
| [SetContents](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetContents.md) | boolean | Sets annotation contents. |
| [SetCreationDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetCreationDate.md) | boolean | Sets annotation creation date. |
| [SetDashPattern](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetDashPattern.md) | boolean | Sets annotation dash pattern. |
| [SetDisplay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetDisplay.md) | boolean | Sets annotation display type. |
| [SetFillColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetFillColor.md) | boolean | Sets annotation fill color. |
| [SetModDate](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetModDate.md) | boolean | Sets annotation last modification date. |
| [SetOpacity](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetOpacity.md) | boolean | Sets annotation opacity. |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetPosition.md) | boolean | Sets annotation position. |
| [SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetRect.md) | boolean | Sets annotation rect. |
| [SetSubject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetSubject.md) | boolean | Sets annotation subject. |
| [SetUniqueName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetUniqueName.md) | boolean | Sets annotation unique name. |
| [SetVertices](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiPolygonAnnotation/Methods/SetVertices.md) | boolean | Sets vertices to polygon annot. |

# GetDrawingsByPlaceholderType

Returns an array of drawings by the specified placeholder type.

## Syntax

```javascript
expression.GetDrawingsByPlaceholderType(sType);
```

`expression` - A variable that represents an [ApiMaster](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/ApiMaster.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| sType | Required | [PlaceholderType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/PlaceholderType.md) |  | The placeholder type. |

## Returns

[Drawing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/presentation-api/Enumeration/Drawing.md)[]

## Example

Get all drawings by placeholder type from a slide master.

```javascript editor-pptx
// Retrieve drawings using GetDrawingsByPlaceholderType, specifying the placeholder type.

// Delete all drawings with the specified placeholder type from the master.

const presentation = Api.GetPresentation();
const slide = presentation.GetSlideByIndex(0);
const master = presentation.GetMaster(0);
const aDrawingsWithPh = master.GetDrawingsByPlaceholderType("title");
for (let i = 0; i < aDrawingsWithPh.length; i++) {
	aDrawingsWithPh[i].Delete();
}
```

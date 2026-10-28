# SetBullet

Sets the bullet or numbering to the current paragraph.

## Syntax

```javascript
expression.SetBullet(oBullet);
```

`expression` - A variable that represents an [ApiParaPr](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiParaPr.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| oBullet | Required | [ApiBullet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBullet.md) \| null \| undefined |  | The bullet object created with the [Api#CreateBullet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateBullet.md) or [Api#CreateNumbering](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Api/Methods/CreateNumbering.md) method. |

## Returns

This method doesn't return any data.

## Example

Add a bullet point to a paragraph using the paragraph properties in a PDF.

```javascript editor-pdf
// How do I add a bullet to a paragraph in a PDF?

// Create a bulleted list item in a paragraph in a PDF.

const doc = Api.GetDocument();
const page = doc.GetPage(0);

const gs1 = Api.CreateGradientStop(Api.RGB(255, 213, 191), 0);
const gs2 = Api.CreateGradientStop(Api.RGB(255, 111, 61), 100000);
const fill = Api.CreateRadialGradientFill([gs1, gs2]);
const stroke = Api.CreateStroke(0, Api.CreateNoFill());
const shape = Api.CreateShape("flowChartMagneticTape", 150 * 36000, 65 * 36000, fill, stroke);
shape.SetPosition(608400, 1267200);

const docContent = shape.GetContent();
const paragraph = docContent.GetElement(0);
const paraPr = paragraph.GetParaPr();
const bullet = Api.CreateBullet("-");
paraPr.SetBullet(bullet);
paragraph.AddText(" This is an example of the bulleted paragraph.");
page.AddObject(shape);
```

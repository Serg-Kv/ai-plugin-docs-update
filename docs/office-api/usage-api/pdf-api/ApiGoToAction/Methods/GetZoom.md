# GetZoom

Gets zoom for action

## Syntax

```javascript
expression.GetZoom();
```

`expression` - A variable that represents an [ApiGoToAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

number \| null \| undefined

## Example

This example creates a GoTo action with xyz type and gets its zoom level.

```javascript editor-pdf
let doc = Api.GetDocument();
let page = doc.GetPage(0);
let buttonField = Api.CreateButtonField([10, 10, 100, 30]);
page.AddObject(buttonField);

let goToAction = Api.CreateGoToAction(0, "xyz", 1.5, [0, 0, 200, 300]);
let widgets = buttonField.GetAllWidgets();
widgets[0].GetActions().SetMouseUp(goToAction);

let zoom = goToAction.GetZoom();
console.log('GoTo zoom: ' + zoom);
```

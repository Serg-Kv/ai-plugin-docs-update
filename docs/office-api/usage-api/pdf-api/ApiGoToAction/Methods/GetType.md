# GetType

Gets goto type

## Syntax

```javascript
expression.GetType();
```

`expression` - A variable that represents an [ApiGoToAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiGoToAction.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[GoToType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/GoToType.md)

## Example

This example creates a GoTo action and gets its destination type.

```javascript editor-pdf
let doc = Api.GetDocument();
let page = doc.GetPage(0);
let buttonField = Api.CreateButtonField([10, 10, 100, 30]);
page.AddObject(buttonField);

let goToAction = Api.CreateGoToAction(0, "fitH", null, [0, 0, 200, 300]);
let widgets = buttonField.GetAllWidgets();
widgets[0].GetActions().SetMouseUp(goToAction);

console.log('GoTo type: ' + goToAction.GetType());
```

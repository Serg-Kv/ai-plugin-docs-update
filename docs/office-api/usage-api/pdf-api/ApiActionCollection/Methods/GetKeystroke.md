# GetKeystroke

Gets Keystroke action.

## Syntax

```javascript
expression.GetKeystroke();
```

`expression` - A variable that represents an [ApiActionCollection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiJsAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiJsAction.md)

## Example

This example gets the Keystroke action from a text field's action collection.

```javascript editor-pdf
let doc = Api.GetDocument();
let page = doc.GetPage(0);
let textField = Api.CreateTextField([10, 10, 160, 30]);
page.AddObject(textField);

let keystrokeAction = Api.CreateJsAction("AFNumber_Keystroke(2, 0, 0, 0, '$', true);");
let widgets = textField.GetAllWidgets();
let actions = widgets[0].GetActions();
actions.SetKeystroke(keystrokeAction);

let action = actions.GetKeystroke();
console.log('Keystroke action script: ' + action.GetScript());
```

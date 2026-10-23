# GetScaleHow

Gets button widget scale when type

## Syntax

```javascript
expression.GetScaleHow();
```

`expression` - A variable that represents an [ApiButtonWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ButtonScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ButtonScaleHow.md)

## Example

Determine how a button icon is scaled in a PDF.

```javascript editor-pdf
// How do I check the icon scaling method for a button in a PDF?

// Retrieve the icon scaling option for a button widget in a PDF.

let doc = Api.GetDocument();
let page = doc.GetPage(0);
let buttonField = Api.CreateImageField([10, 10, 120, 100]);
page.AddObject(buttonField);

let widgets = buttonField.GetAllWidgets();
widgets[0].SetLayout('iconTextV');
widgets[0].SetScaleHow('proportional');
widgets[0].SetLabel('Scale how is: ' + widgets[0].GetScaleHow());
```

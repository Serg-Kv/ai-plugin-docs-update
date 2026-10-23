# GetBorderColor

Gets widget border color.

Inherited from [ApiBaseWidget.GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget/Methods/GetBorderColor.md).

## Syntax

```javascript
expression.GetBorderColor();
```

`expression` - A variable that represents an [ApiButtonWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined

## Example

Read the border color of a form field widget in a PDF.

```javascript editor-pdf
// How do I get the border color of a widget in a PDF?

// Retrieve and display the outline color of a form field in a PDF.

let doc = Api.GetDocument();
let page = doc.GetPage(0);
let textField = Api.CreateTextField([10, 10, 160, 30]);
page.AddObject(textField);

textField.AddWidget(0, [10, 40, 160, 60]);
let widgets = textField.GetAllWidgets();
let rgbColor = Api.RGB(255, 100, 0);
widgets.forEach(function(widget) {
    widget.SetBorderColor(rgbColor);
});
let borderColor = widgets[0].GetBorderColor();
textField.SetValue('Widgets border color is: ' + borderColor.R + ',' + borderColor.G + ',' + borderColor.B);
```

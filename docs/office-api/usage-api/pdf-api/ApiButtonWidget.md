# ApiButtonWidget

Class representing a button widget.

ApiButtonWidget is a subclass of [ApiBaseWidget](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiBaseWidget.md).

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/Delete.md) | boolean | Removes widget from parent field. |
| [GetActions](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetActions.md) | [ApiActionCollection](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiActionCollection.md) | Gets actions collection. |
| [GetActionsJSON](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetActionsJSON.md) | JSON | Gets all field actions in json format. |
| [GetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBackgroundColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets widget background color. |
| [GetBehavior](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBehavior.md) | [ButtonBehavior](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ButtonBehavior.md) | Gets button widget behavior. |
| [GetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBorderColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets widget border color. |
| [GetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBorderStyle.md) | [WidgetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/WidgetBorderStyle.md) | Gets widget border style. |
| [GetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetBorderWidth.md) | [WidgetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/WidgetBorderWidth.md) | Gets widget border width. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetClassType.md) | "buttonWidget" | Returns a type of the ApiButtonWidget class. |
| [GetIconXPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetIconXPos.md) | [percentage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/percentage.md) | Gets button widget icon x position. |
| [GetIconYPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetIconYPos.md) | [percentage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/percentage.md) | Gets button widget icon y position. |
| [GetInternalId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetInternalId.md) | string | Returns an internal ID of the current field widget. |
| [GetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetLabel.md) | string \| null \| undefined | Gets label from button widget field. |
| [GetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetLayout.md) | [ButtonLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ButtonLayout.md) | Gets button widget layout type |
| [GetParent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetParent.md) | [ApiField](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ApiField.md) | Gets parent field. |
| [GetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetPosition.md) | [Point](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Point.md) | Gets widget position. |
| [GetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetRect.md) | [Rect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/Rect.md) | Sets field rect. |
| [GetScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetScaleHow.md) | [ButtonScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ButtonScaleHow.md) | Gets button widget scale when type |
| [GetScaleWhen](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetScaleWhen.md) | [ButtonScaleWhen](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/ButtonScaleWhen.md) | Gets button widget scale when type |
| [GetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetTextAlign.md) | [WidgetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/WidgetTextAlign.md) \| undefined | Gets widget text alignment. |
| [GetTextColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetTextColor.md) | [ApiColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiColor.md) \| null \| undefined | Gets widget text color. |
| [GetTextSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/GetTextSize.md) | [hps](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/Enumeration/hps.md) | Gets widget text size. |
| [IsAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/IsAutoFit.md) | boolean | Checks if text is autofit. |
| [IsFitBounds](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/IsFitBounds.md) | boolean | Checks if button widget is fit bounds. |
| [SetAutoFit](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetAutoFit.md) | boolean | Sets text autofit. |
| [SetBackgroundColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBackgroundColor.md) | boolean | Sets widget background color. |
| [SetBehavior](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBehavior.md) | boolean | Sets button widget behavior. |
| [SetBorderColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBorderColor.md) | boolean | Sets widget border color. |
| [SetBorderStyle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBorderStyle.md) | boolean | Sets widget border style. |
| [SetBorderWidth](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetBorderWidth.md) | boolean | Sets widget border width. |
| [SetFitBounds](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetFitBounds.md) | boolean | Sets button widget fit bounds. |
| [SetIconXPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetIconXPos.md) | boolean | Sets button widget icon x position. |
| [SetIconYPos](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetIconYPos.md) | boolean | Sets button widget icon y position. |
| [SetImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetImage.md) | boolean | Sets image to button widget field. |
| [SetLabel](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetLabel.md) | boolean | Sets label to button widget field. |
| [SetLayout](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetLayout.md) | boolean | Sets button widget layout type |
| [SetPosition](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetPosition.md) | boolean | Sets widget position. |
| [SetRect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetRect.md) | boolean | Sets field rect. |
| [SetScaleHow](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetScaleHow.md) | boolean | Sets button widget scale how type |
| [SetScaleWhen](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetScaleWhen.md) | boolean | Sets button widget scale when type |
| [SetTextAlign](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetTextAlign.md) | boolean | Sets widget text alignment. |
| [SetTextColor](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetTextColor.md) | boolean | Sets widget text color. |
| [SetTextSize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/pdf-api/ApiButtonWidget/Methods/SetTextSize.md) | boolean | Sets widget text size. |

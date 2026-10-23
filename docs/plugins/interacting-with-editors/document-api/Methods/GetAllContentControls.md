# GetAllContentControls

Returns information about all the content controls that have been added to the page.

## Syntax

```javascript
expression.GetAllContentControls();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[ContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControl.md)[]

## Example

```javascript
window.Asc.plugin.init = function () {
    window.Asc.plugin.executeMethod("GetAllContentControls", null, function (controls) {
        for (var i = 0; i < controls.length; i++) {
            if (controls[i].Tag === "{tag}") {
                window.Asc.plugin.executeMethod("SelectContentControl", [controls[i].InternalId]);
                break;
            }
        }
    });
};
```

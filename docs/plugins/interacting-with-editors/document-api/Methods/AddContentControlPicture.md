# AddContentControlPicture

Adds an empty content control picture to the document.

## Syntax

```javascript
expression.AddContentControlPicture(commonPr);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| commonPr | Optional | [ContentControlProperties](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControlProperties.md) | \{\} | The common content control properties. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("AddContentControlPicture", [{"Id" : 7, "Tag" : "{tag}", "Lock" : 0}]);
```

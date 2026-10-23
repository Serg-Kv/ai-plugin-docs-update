# RemoveContentControls

Removes several content controls.

## Syntax

```javascript
expression.RemoveContentControls(arrDocuments);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| arrDocuments | Required | [ContentControl](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/ContentControl.md)[] |  | An array of content control internal IDs. Example: [\{"InternalId": "5_556"\}]. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("RemoveContentControls", [[{"InternalId": "5_556"}]]);
```

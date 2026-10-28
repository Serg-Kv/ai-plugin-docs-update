# ReplaceCurrentWord

Replaces the current word with the specified string.

## Syntax

```javascript
expression.ReplaceCurrentWord(replaceString, type);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| replaceString | Required | string |  | Replacement string. |
| type | Optional | [TextPartType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/TextPartType.md) | "entirely" | Specifies if the whole word or only its part will be replaced. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod ("ReplaceCurrentWord", ["ONLYOFFICE", "entirely"]);
```

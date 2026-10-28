# SelectAnnotationRange

Selects text in a document using a given annotation.

:::note
This functionality is available in paid ONLYOFFICE Docs editions.
:::

## Syntax

```javascript
expression.SelectAnnotationRange(annotation);
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| annotation | Required | [TextAnnotation](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Enumeration/TextAnnotation.md) |  | The annotation selection object. |

## Returns

This method doesn't return any data.

## Example

```javascript
window.Asc.plugin.executeMethod("SelectAnnotationRange", [{
    paragraphId: "p1",
    rangeId: "a1",
    name: "grammar"
}]);
```

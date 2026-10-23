# GetAllComments

Returns all the comments from the document.

## Syntax

```javascript
expression.GetAllComments();
```

`expression` - A variable that represents an [Api](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

[comment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/presentation-api/Enumeration/comment.md)[]

## Example

```javascript
window.Asc.plugin.executeMethod ("GetAllComments", null, function (comments) {
    Comments = comments;
    addComments (comments);
});
```

# SetPicture

Sets the content (image) for the picture content control.

The URL should be an internet link to the image.

## Syntax

```javascript
expression.SetPicture(imageUrl);
```

`expression` - A variable that represents an [ApiBlockLvlSdt](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiBlockLvlSdt.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Default** | **Description** |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| imageUrl | Required | string |  | The URL of the image to be used for the content control. Currently, only internet URLs are supported. |

## Returns

boolean

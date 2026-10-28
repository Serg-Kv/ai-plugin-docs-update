---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TRejectedFile

A file the [SDKMode.Uploader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Uploader) dialog refused before uploading. Nested in [TUploaderUploadError.rejectedFiles](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TUploaderUploadError.md#rejectedFiles).

```ts
type TRejectedFile = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `errors` | [`TUploadRejection`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TUploadRejection.md)[] | Why the file was rejected. See [TUploadRejection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TUploadRejection.md). |
| `fileName` | `string` | Name of the rejected file. |
| `fileSize` | `number` | Size of the rejected file in bytes. |
| `fileType` | `string` | MIME type of the rejected file. |

</APITable>

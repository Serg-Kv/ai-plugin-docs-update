---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TUploaderUploadResult

One element of the [TFrameEvents.onUploadSuccess](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onUploadSuccess) payload in [SDKMode.Uploader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Uploader):
the portal's API envelope around the stored file.

```ts
type TUploaderUploadResult = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `count` | `number` | Number of items in `response`. |
| `response` | [`TUploadedFile`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TUploadedFile.md) | The stored file. See [TUploadedFile](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TUploadedFile.md). |
| `status` | `number` | HTTP status of the portal's response. |
| `statusCode` | `number` | HTTP status of the portal's response (duplicate of `status`). |

</APITable>

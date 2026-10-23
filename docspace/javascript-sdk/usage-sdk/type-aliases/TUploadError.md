---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TUploadError

Payload of [TFrameEvents.onUploadError](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onUploadError) in [SDKMode.Forms](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Forms) and [SDKMode.Personal](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Personal):
the file transferred with [SDKInstance.upload](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#upload) that the frame could not store.

```ts
type TUploadError = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `fileName` | `string` | Name of the rejected file. |
| `message` | `string` | Error message reported by the frame. |
| `uploadId` | `number` | Correlation ID the SDK assigned to the `upload` call. |

</APITable>

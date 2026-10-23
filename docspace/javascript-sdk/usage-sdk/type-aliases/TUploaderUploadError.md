---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TUploaderUploadError

Payload of [TFrameEvents.onUploadError](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onUploadError) in [SDKMode.Uploader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Uploader): the batch failed or some files were refused.

```ts
type TUploaderUploadError = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `error` | `string` | Error message. |
| `rejectedFiles` | [`TRejectedFile`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRejectedFile.md)[] | Files refused by the dialog's validation, when the error is a validation failure. See [TRejectedFile](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRejectedFile.md). |

</APITable>

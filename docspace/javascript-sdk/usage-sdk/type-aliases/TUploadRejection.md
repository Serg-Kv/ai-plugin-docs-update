---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TUploadRejection

One reason a file was rejected by the [SDKMode.Uploader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Uploader) dialog. Nested in [TRejectedFile.errors](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRejectedFile.md#errors).

```ts
type TUploadRejection = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `code` | `string` | Machine-readable reason (`"file-invalid-type"`, `"file-too-large"`, …). |
| `message` | `string` | Human-readable description. |

</APITable>

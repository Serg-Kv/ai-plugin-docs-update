---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TEditorOpenPayload

Payload of [TFrameEvents.onEditorOpen](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onEditorOpen): the file the frame is about to open plus the
requested action. When the user creates a new document in [SDKMode.Manager](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Manager), the payload
is the created file and `action` is absent.

```ts
type TEditorOpenPayload = TFileInfo & object;
```

## Type Declaration

<APITable>

| Name | Type | Description |
| ------ | ------ | ------ |
| `action` | [`TEditorAction`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TEditorAction.md) | Requested editor action. Absent for a document created in [SDKMode.Manager](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Manager). |
| `share` | `string` | Share key of the room when it was opened by an external link; empty otherwise. |

</APITable>

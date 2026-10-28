---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TListResponse\<TFolder\>

Response wrapper for paginated listing methods.
Specialized as [TFilesResponse](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFilesResponse.md) (folders) and [TRoomsResponse](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRoomsResponse.md) (rooms).

```ts
type TListResponse<TFolder> = object;
```

## Type Parameters

<APITable>

| Type Parameter | Description |
| ------ | ------ |
| `TFolder` | The folder-like entry type: [TFolderInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFolderInfo.md) or [TRoomInfo](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRoomInfo.md). |

</APITable>

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `count` | `number` | Number of items returned. |
| `current` | [`TFolderInfo`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFolderInfo.md) | Current folder info. |
| `files` | [`TFileInfo`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFileInfo.md)[] | File entries. |
| `folders` | `TFolder`[] | Folder or room entries. |
| `new` | `number` | Count of new items. |
| `pathParts` | [`TPathParts`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TPathParts.md)[] | Breadcrumb path. |
| `startIndex` | `number` | Pagination start index. |
| `total` | `number` | Total items available. |

</APITable>

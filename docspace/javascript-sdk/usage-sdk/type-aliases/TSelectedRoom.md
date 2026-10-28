---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TSelectedRoom

One selected room in the [SDKMode.RoomSelector](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#RoomSelector) payload. [TFrameEvents.onSelectCallback](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onSelectCallback)
receives an **array** of these; other fields of the selector row pass through unchanged.

```ts
type TSelectedRoom = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `icon` | `string` | Room icon URL. |
| `id` | `string` \| `number` | Room ID. |
| `label` | `string` | Room title. |
| `requestTokens` | [`TRequestTokenInfo`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TRequestTokenInfo.md)[] | External links of a public or shared room; `requestTokens[0].requestToken` is the key for [SDKMode.PublicRoom](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#PublicRoom). Absent for rooms without links. |
| `roomType` | `number` | Numeric room type. See [RoomType](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/RoomType.md). |
| `shared` | `boolean` | Whether the room has an external link. |

</APITable>

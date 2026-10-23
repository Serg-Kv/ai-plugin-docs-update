---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/enums/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# SelectorFilterType

The content filter for selector modes ([SDKMode.RoomSelector](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#RoomSelector), [SDKMode.FileSelector](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#FileSelector)).
Passed via [TFrameConfig.selectorType](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#selectorType).

## Example

```typescript
sdk.init({ mode: SDKMode.FileSelector, selectorType: SelectorFilterType.RoomsOnly, ... });
```

## Enumeration Members

<APITable>

| Enumeration Member | Value | Description |
| ------ | ------ | ------ |
| `All` | `"all"` | No filter — shows rooms and user folders. |
| `RoomsOnly` | `"roomsOnly"` | Shows only rooms. |
| `UserOnly` | `"userFolderOnly"` | Shows only the current user's personal folders. API value: `"userFolderOnly"`. |

</APITable>

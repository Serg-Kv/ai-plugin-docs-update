---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TInitConfig

Configuration accepted by the mode-specific `SDK.init*` wrappers ([SDK.initManager](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDK.md#initmanager),
[SDK.initPersonal](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDK.md#initpersonal), ...): a [TFrameConfig](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md) whose `mode` is optional because the
wrapper sets it. Only `frameId` and `src` are required. [SDK.init](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDK.md#init) takes a full
[TFrameConfig](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md) with `mode`.

```ts
type TInitConfig = Omit<TFrameConfig, "mode"> & object;
```

## Type Declaration

<APITable>

| Name | Type |
| ------ | ------ |
| `mode` | [`TFrameMode`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameMode.md) |

</APITable>

## Example

```typescript
const config: TInitConfig = { frameId: "ds-frame", src: "https://portal.example.com" };
sdk.initManager(config);
```

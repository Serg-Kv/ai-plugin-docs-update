---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# TNavigatePayload

Payload of [TFrameEvents.onNavigate](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onNavigate).

```ts
type TNavigatePayload = object;
```

## Properties

<APITable>

| Property | Type | Description |
| ------ | ------ | ------ |
| `section` | \| [`TFormsSection`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFormsSection.md) \| [`TPersonalSection`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TPersonalSection.md) | The section the frame navigated to: a [TFormsSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFormsSection.md) in [SDKMode.Forms](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Forms), a [TPersonalSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TPersonalSection.md) in [SDKMode.Personal](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Personal). |

</APITable>

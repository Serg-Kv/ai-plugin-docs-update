---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

# TFrameMode

String literal union of all [SDKMode](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md) values.

Accepted by [TFrameConfig.mode](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#mode). Using the [SDKMode](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md) enum constants
is preferred, but plain string literals (e.g. `"manager"`, `"editor"`) are equally valid.

```ts
type TFrameMode = `${SDKMode}`;
```

## Example

```typescript
sdk.init({ frameId: 'ds-frame', src: 'https://portal.example.com', mode: 'manager' });
// equivalent to:
sdk.init({ frameId: 'ds-frame', src: 'https://portal.example.com', mode: SDKMode.Manager });
```

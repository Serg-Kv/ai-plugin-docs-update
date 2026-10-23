---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

# TCustomActionSection

A section a custom action can be limited to: a [TManagerSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TManagerSection.md), a [TPersonalSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TPersonalSection.md)
or a [TFormsSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFormsSection.md), matched against the mode the frame runs in.

```ts
type TCustomActionSection = 
  | TManagerSection
  | TPersonalSection
  | TFormsSection;
```

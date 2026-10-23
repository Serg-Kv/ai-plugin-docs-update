---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

# TPersonalSection

Navigation sections available in [SDKMode.Personal](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Personal) mode.
Used as [TFrameConfig.personalDestination](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#personalDestination) for the initial section and by
[SDKInstance.navigateSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#navigatesection) to switch sections at runtime.

```ts
type TPersonalSection = 
  | "my-documents"
  | "favorites"
  | "recent"
  | "shared-with-me"
  | "trash"
  | "settings";
```

## Example

```typescript
const personal = sdk.initPersonal({
  frameId: "ds-personal",
  src: "https://portal.example.com",
  personalDestination: "favorites",
});
await personal.navigateSection("trash");
```

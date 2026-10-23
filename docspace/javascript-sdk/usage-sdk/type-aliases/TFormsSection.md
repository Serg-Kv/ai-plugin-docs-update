---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/types/index.ts
---

# TFormsSection

Navigation sections available in [SDKMode.Forms](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md#Forms) mode.
Used by [SDKInstance.navigateSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#navigatesection).

```ts
type TFormsSection = "my-forms" | "in-progress" | "completed-forms" | "library" | "settings";
```

## Example

```typescript
await instance.navigateSection("completed-forms");
```

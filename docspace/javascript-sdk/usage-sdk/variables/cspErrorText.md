---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/constants/index.ts
---

# cspErrorText

Error message shown when the host domain is not in the ONLYOFFICE Apps CSP allowlist.
Displayed inside the iframe via `srcdoc` when [TFrameConfig.checkCSP](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#checkCSP) is `true` and validation fails.

```ts
const cspErrorText: "The current domain is not set in the Content Security Policy (CSP) settings.";
```

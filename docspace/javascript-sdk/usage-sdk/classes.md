---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/tools/docs/sections.mjs
---

# Classes

The classes an integration works with. `SDK` creates frames and keeps them in a registry, `SDKInstance` drives one embedded iframe and exposes the methods that call into it, and `SDKError` is what a failed call rejects with.

## Overview

The following classes are available:

| Class | Description |
| --- | --- |
| [`SDK`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDK.md) | Manages multiple [SDKInstance](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md) objects and provides convenience wrappers for each [SDKMode](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/enumerations/SDKMode.md). |
| [`SDKError`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKError.md) | The SDK's structured error class. |
| [`SDKInstance`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md) | Manages a single ONLYOFFICE Apps iframe, handles postMessage communication, and exposes methods for operating on the embedded ONLYOFFICE Apps UI. |

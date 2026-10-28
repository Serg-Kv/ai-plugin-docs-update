---
sidebar_position: -12
---

# Security

ONLYOFFICE Docs uses token-based validation to ensure that requests between services have not been tampered with. Every request — whether it comes from the **document editor** initializing with a [`config`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/config.md), or passes between the **document storage service** and the **document editing service**, **document command service**, **document conversion service**, or **document builder service** — can carry a cryptographic token that the receiving side verifies before acting on the request.

Tokens are generated using the [JSON Web Token](https://jwt.io/) (JWT) standard and signed with a secret key shared between the integrator's server and ONLYOFFICE Docs. When a token is present, ONLYOFFICE Docs validates it and uses the data from the token payload instead of the corresponding request parameters. If the token is missing or invalid, the request is rejected.

See the [Signature](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/additional-api/signature.md) section for setup instructions and code examples.

:::warning
Local links (URLs pointing to private or internal addresses) always require a token. Include a token when using local links in the following methods: [insertImage](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#insertimage), [setHistoryData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#sethistorydata), [setMailMergeRecipients](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setmailmergerecipients), [setReferenceData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setreferencedata), [setReferenceSource](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setreferencesource), [setRequestedDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setrequesteddocument), [setRequestedSpreadsheet](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setrequestedspreadsheet), [setRevisedFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/methods.md#setrevisedfile). A token is also required when specifying a local URL for [opening](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/usage-api/config/document.md#url) or [conversion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/additional-api/conversion-api/request.md#url).
:::

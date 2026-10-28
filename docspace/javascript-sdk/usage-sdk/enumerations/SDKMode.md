---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-sdk-js/blob/master/src/enums/index.ts
---

import APITable from '@site/src/components/APITable/APITable';

# SDKMode

The SDK initialization mode. Passed via [TFrameConfig.mode](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#mode).
Determines the UI and available functionality of the embedded frame.

## Example

```typescript
sdk.init({ mode: SDKMode.Manager, frameId: "ds-frame", src: "https://portal.example.com" });
```

## Enumeration Members

<APITable>

| Enumeration Member | Value | Description |
| ------ | ------ | ------ |
| `Chat` | `"chat"` | AI chat interface. Full-page conversation UI, bound to an AI agent when [TFrameConfig.agentId](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#agentId) is set, to the current user otherwise. |
| `Editor` | `"editor"` | Document editor. Requires [TFrameConfig.id](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#id) — the file identifier to open for editing. |
| `FileSelector` | `"file-selector"` | File picker dialog. Returns the selected file via [TFrameEvents.onSelectCallback](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onSelectCallback). Filterable by [TFrameConfig.selectorType](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#selectorType). |
| `Forms` | `"forms"` | Forms gallery. Displays forms for the room specified by [TFrameConfig.id](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#id). Supports [TFrameConfig.showMenu](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#showMenu) to toggle the side panel. |
| `Manager` | `"manager"` | File/folder browser. Displays a list of entities at [TFrameConfig.rootPath](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#rootPath). Supports CRUD operations on rooms, folders, and files. Forces [TFrameConfig.noLoader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#noLoader) to `false`. |
| `Personal` | `"personal"` | Personal files browser. File/folder manager for the user's personal space (My Documents, Favorites, Recent, Shared with me, Trash). Uses [TFrameConfig.personalDestination](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#personalDestination) to pick the initial section; has no navigation menu of its own, so the host switches sections with [SDKInstance.navigateSection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#navigatesection). |
| `PublicRoom` | `"public-room"` | Public room view. Grants anonymous access to view, edit, comment on, and review documents. Requires [TFrameConfig.requestToken](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#requestToken). |
| `RoomSelector` | `"room-selector"` | Room picker dialog. Returns the selected room via [TFrameEvents.onSelectCallback](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameEvents.md#onSelectCallback). |
| `System` | `"system"` | Headless mode. Renders a blank page with a loader; used to call session methods ([SDKInstance.login](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#login), [SDKInstance.logout](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md#logout)) without UI. Forces [TFrameConfig.noLoader](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#noLoader) to `false`. |
| `Uploader` | `"uploader"` | File upload interface. Uploads files to the folder specified by [TFrameConfig.id](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#id). |
| `Viewer` | `"viewer"` | Read-only document viewer. Requires [TFrameConfig.id](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/type-aliases/TFrameConfig.md#id) — the file identifier to open for viewing. |

</APITable>

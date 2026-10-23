---
description: Overview of basic Embed SDK samples, grouped by SDK area.
tags: ["Apps", "Embed SDK", "Integration"]
---

# Basic samples

These samples each demonstrate a single ONLYOFFICE Apps Embed SDK mode or method in isolation. Use them as a quick reference before combining several calls into a real integration, like the ones in [Advanced samples](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/advanced-samples.md).

Not every SDK method has a dedicated sample yet. For the complete list, see the [SDK](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDK.md) reference for the init methods and the [SDKInstance](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/usage-sdk/classes/SDKInstance.md) reference for the instance methods.

## Authentication and session

| Sample | Description |
| --- | --- |
| [Create password hash](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/create-hash.md) | Generate a password hash using the ONLYOFFICE Apps JS SDK. |
| [Login](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/login.md) | Log in to ONLYOFFICE Apps using the JS SDK with password hashing. |
| [Logout](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/logout.md) | Log out a user from the ONLYOFFICE Apps session using the JS SDK. |
| [Get hash settings](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-hash-settings.md) | Retrieve hash settings from the ONLYOFFICE Apps frame using the JS SDK. |
| [Get user info](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-user-info.md) | Retrieve user information using the ONLYOFFICE Apps JS SDK. |

## Frame initialization

| Sample | Description |
| --- | --- |
| [Initialize frame](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-frame.md) | Initialize an ONLYOFFICE Apps frame in the mode set by the `mode` config field. |
| [Initialize manager](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-manager.md) | Initialize the ONLYOFFICE Apps manager using the JS SDK. |
| [Initialize editor](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-editor.md) | Open a document in the ONLYOFFICE Apps editor using the JS SDK. |
| [Initialize viewer](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-viewer.md) | Embed a read-only document viewer using the JS SDK. |
| [Initialize file selector](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-file-selector.md) | Initialize the ONLYOFFICE Apps file selector using the JS SDK. |
| [Initialize room selector](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-room-selector.md) | Embed the room selection interface using the JS SDK. |
| [Initialize system](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/init-system.md) | Initialize the ONLYOFFICE Apps system interface using the JS SDK. |
| [Destroy frame](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/destroy-frame.md) | Remove the embedded ONLYOFFICE Apps iframe using the JS SDK. |
| [Mark iframe as loaded](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/mark-iframe-as-loaded.md) | Mark the ONLYOFFICE Apps iframe as loaded using the JS SDK. |

## Frame configuration and UI

| Sample | Description |
| --- | --- |
| [Get config](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-config.md) | Retrieve the embedded frame configuration using the JS SDK. |
| [Set config](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/set-config.md) | Update the embedded frame configuration using the JS SDK. |
| [Set list view](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/set-list-view.md) | Change the file list display mode using the JS SDK. |
| [Open modal](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/open-modal.md) | Open a modal window in ONLYOFFICE Apps using the JS SDK. |
| [Get selection](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-selection.md) | Retrieve the current selection in ONLYOFFICE Apps using the JS SDK. |

## Rooms and folders

| Sample | Description |
| --- | --- |
| [Create room](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/create-room.md) | Create a new shared room using the ONLYOFFICE Apps JS SDK. |
| [Get rooms](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-rooms.md) | Retrieve available rooms using the ONLYOFFICE Apps JS SDK. |
| [Create folder](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/create-folder.md) | Create a folder in an ONLYOFFICE Apps room using the JS SDK. |
| [Get folders](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-folders.md) | Retrieve a list of folders from a room using the JS SDK. |
| [Get folder info](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-folder-info.md) | Retrieve current folder information using the JS SDK. |

## Files

| Sample | Description |
| --- | --- |
| [Create file](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/create-file.md) | Create a new file inside an ONLYOFFICE Apps room using the JS SDK. |
| [Get files](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-files.md) | Retrieve a list of files from a room using the JS SDK. |
| [Get files and folders list](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/get-files-and-folders-list.md) | Retrieve files and folders from a room using the JS SDK. |

## Tags

| Sample | Description |
| --- | --- |
| [Create tag](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/create-tag.md) | Create a custom tag in ONLYOFFICE Apps using the JS SDK. |
| [Add tags to room](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/add-tags-to-room.md) | Add custom tags to an ONLYOFFICE Apps room using the JS SDK. |
| [Remove tags from room](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/javascript-sdk/samples/basic-samples/remove-tags-from-room.md) | Remove tags from an ONLYOFFICE Apps room using the JS SDK. |

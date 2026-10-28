# ONLYOFFICE Apps Rooms API

The browsable version of this reference, with a request builder and code samples, is published at
[https://api.onlyoffice.com/docspace/api-backend/usage-api/](https://api.onlyoffice.com/docspace/api-backend/usage-api/).

All URIs are relative to *https://yourportal.onlyoffice.com*, where the host is the address of your Apps instance.

## Rooms

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**addRoomTags**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/add-room-tags.md) | **PUT** /api/2.0/files/rooms/\{id\}/tags | Attach tags to a room |
| [**archiveRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/archive-room.md) | **PUT** /api/2.0/files/rooms/\{id\}/archive | Archive a room |
| [**changeRoomCover**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/change-room-cover.md) | **POST** /api/2.0/files/rooms/\{id\}/cover | Change the room cover |
| [**createRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room.md) | **POST** /api/2.0/files/rooms | Create a room |
| [**createRoomFromTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room-from-template.md) | **POST** /api/2.0/files/rooms/fromtemplate | Create a room from the template |
| [**createRoomLogo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room-logo.md) | **POST** /api/2.0/files/rooms/\{id\}/logo | Set the room logo |
| [**createRoomTag**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room-tag.md) | **POST** /api/2.0/files/tags | Create a room tag |
| [**createRoomTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room-template.md) | **POST** /api/2.0/files/roomtemplate | Create a room template |
| [**createRoomThirdParty**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/create-room-third-party.md) | **POST** /api/2.0/files/rooms/thirdparty/\{id\} | Create a third-party room |
| [**deleteCustomTags**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/delete-custom-tags.md) | **DELETE** /api/2.0/files/tags | Delete the custom room tags |
| [**deleteRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/delete-room.md) | **DELETE** /api/2.0/files/rooms/\{id\} | Remove a room |
| [**deleteRoomLogo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/delete-room-logo.md) | **DELETE** /api/2.0/files/rooms/\{id\}/logo | Remove a room logo |
| [**deleteRoomTags**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/delete-room-tags.md) | **DELETE** /api/2.0/files/rooms/\{id\}/tags | Detach tags from a room |
| [**getExternalDbSyncStatus**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-external-db-sync-status.md) | **GET** /api/2.0/files/rooms/\{id\}/externaldbsync | Get external DB sync status |
| [**getNewRoomItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-new-room-items.md) | **GET** /api/2.0/files/rooms/\{id\}/news | Get new items in a room |
| [**getPublicSettings**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-public-settings.md) | **GET** /api/2.0/files/roomtemplate/\{id\}/public | Get room template public access |
| [**getRoomAiFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-ai-folder.md) | **GET** /api/2.0/files/rooms/\{id\}/ai | Get the .ai folder of a room |
| [**getRoomCovers**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-covers.md) | **GET** /api/2.0/files/rooms/covers | Get room cover gallery |
| [**getRoomCreatingStatus**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-creating-status.md) | **GET** /api/2.0/files/rooms/fromtemplate/status | Get the room creation progress |
| [**getRoomIndexExport**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-index-export.md) | **GET** /api/2.0/files/rooms/indexexport | Get the room index export |
| [**getRoomInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-info.md) | **GET** /api/2.0/files/rooms/\{id\} | Get room information |
| [**getRoomLinks**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-links.md) | **GET** /api/2.0/files/rooms/\{id\}/links | Get the room links |
| [**getRoomSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-security-info.md) | **GET** /api/2.0/files/rooms/\{id\}/share | Get the room access rights |
| [**getRoomTagsInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-tags-info.md) | **GET** /api/2.0/files/tags | Get available room tags |
| [**getRoomTemplateCreatingStatus**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-room-template-creating-status.md) | **GET** /api/2.0/files/roomtemplate/status | Get room template creation status |
| [**getRoomsFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-rooms-folder.md) | **GET** /api/2.0/files/rooms | Get rooms |
| [**getRoomsNewItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-rooms-new-items.md) | **GET** /api/2.0/files/rooms/news | Get new items in all rooms |
| [**getRoomsPrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/get-rooms-primary-external-link.md) | **GET** /api/2.0/files/rooms/\{id\}/link | Get the room primary external link |
| [**hasTagLinks**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/has-tag-links.md) | **GET** /api/2.0/files/tags/\{tagName\}/haslinks | Check room tag usage |
| [**pinRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/pin-room.md) | **PUT** /api/2.0/files/rooms/\{id\}/pin | Pin a room |
| [**reorderRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/reorder-room.md) | **PUT** /api/2.0/files/rooms/\{id\}/reorder | Reorder room contents |
| [**resendEmailInvitations**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/resend-email-invitations.md) | **POST** /api/2.0/files/rooms/\{id\}/resend | Resend the room invitations |
| [**searchRooms**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/search-rooms.md) | **POST** /api/2.0/files/rooms/search | Search the rooms by metadata |
| [**setPublicSettings**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/set-public-settings.md) | **PUT** /api/2.0/files/roomtemplate/public | Set room template public access |
| [**setRoomLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/set-room-link.md) | **PUT** /api/2.0/files/rooms/\{id\}/links | Set the room external or invitation link |
| [**setRoomSecurity**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/set-room-security.md) | **PUT** /api/2.0/files/rooms/\{id\}/share | Set the room access rights |
| [**startExternalDbSync**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/start-external-db-sync.md) | **POST** /api/2.0/files/rooms/\{id\}/externaldbsync | Start external DB sync |
| [**startRoomIndexExport**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/start-room-index-export.md) | **POST** /api/2.0/files/rooms/\{id\}/indexexport | Start the room index export |
| [**terminateRoomIndexExport**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/terminate-room-index-export.md) | **DELETE** /api/2.0/files/rooms/indexexport | Terminate the room index export |
| [**unarchiveRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/unarchive-room.md) | **PUT** /api/2.0/files/rooms/\{id\}/unarchive | Unarchive a room |
| [**unpinRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/unpin-room.md) | **PUT** /api/2.0/files/rooms/\{id\}/unpin | Unpin a room |
| [**updateRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/update-room.md) | **PUT** /api/2.0/files/rooms/\{id\} | Update a room |
| [**updateRoomTag**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/update-room-tag.md) | **PUT** /api/2.0/files/tags | Rename a room tag |
| [**uploadRoomLogo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/upload-room-logo.md) | **POST** /api/2.0/files/logos | Upload a room logo image |

## Groups

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**addRoomGroup**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/add-room-group.md) | **POST** /api/2.0/files/group | Add a new room group |
| [**changeRoomGroupIcon**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/change-room-group-icon.md) | **POST** /api/2.0/files/group/\{id\}/icon | Change room group icon |
| [**deleteRoomGroup**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/delete-room-group.md) | **DELETE** /api/2.0/files/group/\{id\} | Delete a room group |
| [**getRoomGroupInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/get-room-group-info.md) | **GET** /api/2.0/files/group/\{id\} | Get room group info |
| [**getRoomGroups**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/get-room-groups.md) | **GET** /api/2.0/files/group | List room groups |
| [**updateRoomGroup**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/groups/update-room-group.md) | **PUT** /api/2.0/files/group/\{id\} | Update room group |

## Privacy room

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**deleteKeys**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/privacy-room/delete-keys.md) | **DELETE** /api/2.0/privacyroom/keys/\{id\} | Delete an encryption key |
| [**getUserKeys**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/privacy-room/get-user-keys.md) | **GET** /api/2.0/privacyroom/keys | Get own encryption keys |
| [**getUserKeysForRoom**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/privacy-room/get-user-keys-for-room.md) | **GET** /api/2.0/privacyroom/\{roomId\}/access | Get private room access keys |
| [**replaceKey**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/privacy-room/replace-key.md) | **PUT** /api/2.0/privacyroom/keys | Rotate an encryption key |
| [**setKeys**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/rooms/privacy-room/set-keys.md) | **POST** /api/2.0/privacyroom/keys | Create an encryption key |

## Authorization

### cookieAuth
- **Type**: API key
- **API key parameter name**: asc_auth_key
- **Location**: 

### bearerAuth

- **Type**: HTTP Bearer Token authentication

### asc_auth_key
- **Type**: API key
- **API key parameter name**: asc_auth_key
- **Location**: 

### Basic

- **Type**: HTTP basic authentication

### Bearer

- **Type**: HTTP Bearer Token authentication (JWT)

### ApiKeyBearer
- **Type**: API key
- **API key parameter name**: ApiKeyBearer
- **Location**: HTTP header

### OAuth2

- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: 
- **Scopes**: 
  - read: Read access to protected resources
  - write: Write access to protected resources

### OpenId

### x-signature
- **Type**: API key
- **API key parameter name**: x-signature
- **Location**: 


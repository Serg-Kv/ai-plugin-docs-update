# ONLYOFFICE Apps Files API

The browsable version of this reference, with a request builder and code samples, is published at
[https://api.onlyoffice.com/docspace/api-backend/usage-api/](https://api.onlyoffice.com/docspace/api-backend/usage-api/).

All URIs are relative to *https://yourportal.onlyoffice.com*, where the host is the address of your Apps instance.

## Files

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**addFileToRecent**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/add-file-to-recent.md) | **POST** /api/2.0/files/file/\{fileId\}/recent | Add a file to Recent |
| [**addTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/add-templates.md) | **POST** /api/2.0/files/templates | Add template files |
| [**changeVersionHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/change-version-history.md) | **PUT** /api/2.0/files/file/\{fileId\}/history | Change version history |
| [**checkFillFormDraft**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/check-fill-form-draft.md) | **POST** /api/2.0/files/masterform/\{fileId\}/checkfillformdraft | Open a form draft for filling |
| [**copyFileAs**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/copy-file-as.md) | **POST** /api/2.0/files/file/\{fileId\}/copyas | Copy a file |
| [**createEditSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-edit-session.md) | **POST** /api/2.0/files/file/\{fileId\}/edit_session | Create the editing session |
| [**createFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-file.md) | **POST** /api/2.0/files/\{folderId\}/file | Create a file |
| [**createFileInMyDocuments**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-file-in-my-documents.md) | **POST** /api/2.0/files/@my/file | Create a file in My documents |
| [**createFilePrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-file-primary-external-link.md) | **POST** /api/2.0/files/file/\{id\}/link | Create the file primary external link |
| [**createHtmlFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-html-file.md) | **POST** /api/2.0/files/\{folderId\}/html | Create an HTML file |
| [**createHtmlFileInMyDocuments**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-html-file-in-my-documents.md) | **POST** /api/2.0/files/@my/html | Create an HTML file in My documents |
| [**createTextFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-text-file.md) | **POST** /api/2.0/files/\{folderId\}/text | Create a text file |
| [**createTextFileInMyDocuments**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-text-file-in-my-documents.md) | **POST** /api/2.0/files/@my/text | Create a text file in My documents |
| [**createThumbnails**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/create-thumbnails.md) | **POST** /api/2.0/files/thumbnails | Queue file thumbnails |
| [**deleteFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/delete-file.md) | **DELETE** /api/2.0/files/file/\{fileId\} | Delete a file |
| [**deleteRecent**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/delete-recent.md) | **DELETE** /api/2.0/files/recent | Delete recent files |
| [**deleteTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/delete-templates.md) | **DELETE** /api/2.0/files/templates | Delete template files |
| [**generateXlsx**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/generate-xlsx.md) | **POST** /api/2.0/files/file/\{fileId\}/xlsx | Generate a form answers report |
| [**getAllFormRoles**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-all-form-roles.md) | **GET** /api/2.0/files/file/\{fileId\}/formroles | Get form roles |
| [**getEditDiffUrl**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-edit-diff-url.md) | **GET** /api/2.0/files/file/\{fileId\}/edit/diff | Get changes URL |
| [**getEditHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-edit-history.md) | **GET** /api/2.0/files/file/\{fileId\}/edit/history | Get version history |
| [**getEncryptionInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-encryption-info.md) | **GET** /api/2.0/files/\{fileId\}/access | Get file encryption information |
| [**getFileHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-file-history.md) | **GET** /api/2.0/files/file/\{fileId\}/log | Get file history |
| [**getFileInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-file-info.md) | **GET** /api/2.0/files/file/\{fileId\} | Get file information |
| [**getFileLinks**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-file-links.md) | **GET** /api/2.0/files/file/\{id\}/links | Get file external links |
| [**getFilePrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-file-primary-external-link.md) | **GET** /api/2.0/files/file/\{id\}/link | Get the file primary external link |
| [**getFileVersionInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-file-version-info.md) | **GET** /api/2.0/files/file/\{fileId\}/history | Get file versions |
| [**getFillResult**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-fill-result.md) | **GET** /api/2.0/files/file/fillresult | Get form-filling result |
| [**getFormSubmissions**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-form-submissions.md) | **GET** /api/2.0/files/file/\{fileId\}/submissions | Get form submission results |
| [**getPresignedFileUri**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-presigned-file-uri.md) | **GET** /api/2.0/files/file/\{fileId\}/presigned | Get a signed download address |
| [**getPresignedUri**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-presigned-uri.md) | **GET** /api/2.0/files/file/\{fileId\}/presigneduri | Get file download link |
| [**getProtectedFileUsers**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-protected-file-users.md) | **GET** /api/2.0/files/file/\{fileId\}/protectusers | Get users for document protection |
| [**getReferenceData**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-reference-data.md) | **POST** /api/2.0/files/file/referencedata | Resolve a spreadsheet reference |
| [**getXlsx**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/get-xlsx.md) | **GET** /api/2.0/files/file/\{fileId\}/xlsx | Get form report generation status |
| [**isFormPDF**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/is-form-pdf.md) | **GET** /api/2.0/files/file/\{fileId\}/isformpdf | Check the PDF file |
| [**lockFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/lock-file.md) | **PUT** /api/2.0/files/file/\{fileId\}/lock | Lock a file |
| [**manageFormFilling**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/manage-form-filling.md) | **PUT** /api/2.0/files/file/\{fileId\}/manageformfilling | Perform form filling action |
| [**openEditFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/open-edit-file.md) | **GET** /api/2.0/files/file/\{fileId\}/openedit | Get the editor configuration |
| [**restoreFileVersion**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/restore-file-version.md) | **POST** /api/2.0/files/file/\{fileId\}/restoreversion | Restore a file version |
| [**saveEditingFileFromForm**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/save-editing-file-from-form.md) | **PUT** /api/2.0/files/file/\{fileId\}/saveediting | Save edited file content |
| [**saveFileAsPdf**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/save-file-as-pdf.md) | **POST** /api/2.0/files/file/\{id\}/saveaspdf | Save a file as PDF |
| [**saveFormRoleMapping**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/save-form-role-mapping.md) | **POST** /api/2.0/files/file/\{fileId\}/formrolemapping | Save form role mapping |
| [**setCustomFilterTag**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/set-custom-filter-tag.md) | **PUT** /api/2.0/files/file/\{fileId\}/customfilter | Set the Custom Filter editing mode |
| [**setEncryptionInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/set-encryption-info.md) | **PUT** /api/2.0/files/\{fileId\}/access | Set file encryption information |
| [**setFileExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/set-file-external-link.md) | **PUT** /api/2.0/files/file/\{id\}/links | Set a file external link |
| [**setFileOrder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/set-file-order.md) | **PUT** /api/2.0/files/\{fileId\}/order | Set file order |
| [**setFilesOrder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/set-files-order.md) | **PUT** /api/2.0/files/order | Set order of files |
| [**startEditFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/start-edit-file.md) | **POST** /api/2.0/files/file/\{fileId\}/startedit | Open an editing session |
| [**startFillingFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/start-filling-file.md) | **PUT** /api/2.0/files/file/\{fileId\}/startfilling | Start filling a form |
| [**toggleFileFavorite**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/toggle-file-favorite.md) | **GET** /api/2.0/files/favorites/\{fileId\} | Set the file favorite status |
| [**trackEditFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/track-edit-file.md) | **GET** /api/2.0/files/file/\{fileId\}/trackeditfile | Track an editing session |
| [**updateFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/files/update-file.md) | **PUT** /api/2.0/files/file/\{fileId\} | Update a file |

## Folders

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**checkUpload**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/check-upload.md) | **POST** /api/2.0/files/\{folderId\}/upload/check | Check for upload conflicts |
| [**createFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/create-folder.md) | **POST** /api/2.0/files/folder/\{folderId\} | Create a folder |
| [**createFolderPrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/create-folder-primary-external-link.md) | **POST** /api/2.0/files/folder/\{id\}/link | Create the folder primary external link |
| [**createReportFolderHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/create-report-folder-history.md) | **POST** /api/2.0/files/folder/\{folderId\}/log/report | Start the folder history report generation |
| [**deleteFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/delete-folder.md) | **DELETE** /api/2.0/files/folder/\{folderId\} | Delete a folder |
| [**generateXlsxByFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/generate-xlsx-by-folder.md) | **POST** /api/2.0/files/folder/\{folderId\}/xlsx | Generate XLSX report by folder |
| [**getFavoritesFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-favorites-folder.md) | **GET** /api/2.0/files/@favorites | Get the Favorites section |
| [**getFilesUsedSpace**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-files-used-space.md) | **GET** /api/2.0/files/filesusedspace | Get used space of files |
| [**getFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder.md) | **GET** /api/2.0/files/\{folderId\}/formfilter | Get folder form filter |
| [**getFolderByFolderId**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-by-folder-id.md) | **GET** /api/2.0/files/\{folderId\} | Get a folder by ID |
| [**getFolderHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-history.md) | **GET** /api/2.0/files/folder/\{folderId\}/log | Get folder history |
| [**getFolderInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-info.md) | **GET** /api/2.0/files/folder/\{folderId\} | Get folder information |
| [**getFolderLinks**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-links.md) | **GET** /api/2.0/files/folder/\{id\}/links | Get folder external links |
| [**getFolderPath**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-path.md) | **GET** /api/2.0/files/folder/\{folderId\}/path | Get the folder path |
| [**getFolderPrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folder-primary-external-link.md) | **GET** /api/2.0/files/folder/\{id\}/link | Get the folder primary external link |
| [**getFolders**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-folders.md) | **GET** /api/2.0/files/\{folderId\}/subfolders | Get subfolders |
| [**getFormsFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-forms-folder.md) | **GET** /api/2.0/files/@forms | Get the Forms section |
| [**getMyFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-my-folder.md) | **GET** /api/2.0/files/@my | Get the My documents section |
| [**getNewFolderItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-new-folder-items.md) | **GET** /api/2.0/files/\{folderId\}/news | Get new folder items |
| [**getRecentFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-recent-folder.md) | **GET** /api/2.0/files/recent | Get the Recent section |
| [**getReportFolderHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-report-folder-history.md) | **GET** /api/2.0/files/folder/\{folderId\}/log/report | Get the folder history report generation status |
| [**getRootFolders**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-root-folders.md) | **GET** /api/2.0/files/@root | Get filtered sections |
| [**getTrashFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/get-trash-folder.md) | **GET** /api/2.0/files/@trash | Get the Trash section |
| [**insertFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/insert-file.md) | **POST** /api/2.0/files/\{folderId\}/insert | Insert a file |
| [**insertFileToMyFromBody**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/insert-file-to-my-from-body.md) | **POST** /api/2.0/files/@my/insert | Insert a file into My documents |
| [**renameFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/rename-folder.md) | **PUT** /api/2.0/files/folder/\{folderId\} | Rename a folder |
| [**searchFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/search-folder.md) | **POST** /api/2.0/files/\{folderId\}/search | Search a folder by metadata |
| [**setFolderOrder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/set-folder-order.md) | **PUT** /api/2.0/files/folder/\{folderId\}/order | Set folder order |
| [**setFolderPrimaryExternalLink**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/set-folder-primary-external-link.md) | **PUT** /api/2.0/files/folder/\{id\}/links | Set the folder external link |
| [**terminateReportFolderHistory**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/terminate-report-folder-history.md) | **DELETE** /api/2.0/files/folder/\{folderId\}/log/report | Terminate the folder history report generation |
| [**uploadFile**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/upload-file.md) | **POST** /api/2.0/files/\{folderId\}/upload | Upload a file |
| [**uploadFileToMy**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/folders/upload-file-to-my.md) | **POST** /api/2.0/files/@my/upload | Upload a file to My documents |

## Metadata

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**assignFileTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/assign-file-templates.md) | **PUT** /api/2.0/files/metadata/file/\{fileId\}/templates | Assign templates to a file |
| [**assignFolderTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/assign-folder-templates.md) | **PUT** /api/2.0/files/metadata/folder/\{folderId\}/templates | Assign templates to a folder |
| [**createField**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/create-field.md) | **POST** /api/2.0/files/metadata/templates/\{templateId\}/fields | Add a metadata field |
| [**createTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/create-template.md) | **POST** /api/2.0/files/metadata/templates | Create a metadata template |
| [**deleteField**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/delete-field.md) | **DELETE** /api/2.0/files/metadata/templates/\{templateId\}/fields/\{fieldId\} | Delete a metadata field |
| [**deleteTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/delete-template.md) | **DELETE** /api/2.0/files/metadata/templates/\{templateId\} | Delete a metadata template |
| [**getCascadeProgress**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/get-cascade-progress.md) | **GET** /api/2.0/files/metadata/folder/\{folderId\}/templates/progress | Get cascade progress |
| [**getFileMetadata**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/get-file-metadata.md) | **GET** /api/2.0/files/metadata/file/\{fileId\} | Get file metadata |
| [**getFolderMetadata**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/get-folder-metadata.md) | **GET** /api/2.0/files/metadata/folder/\{folderId\} | Get folder metadata |
| [**getTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/get-template.md) | **GET** /api/2.0/files/metadata/templates/\{templateId\} | Get a metadata template |
| [**getTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/get-templates.md) | **GET** /api/2.0/files/metadata/templates | Get metadata templates |
| [**setFileCustomFields**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/set-file-custom-fields.md) | **PUT** /api/2.0/files/metadata/file/\{fileId\}/customfields | Set file custom fields |
| [**setFileValues**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/set-file-values.md) | **PUT** /api/2.0/files/metadata/file/\{fileId\}/values | Set file metadata values |
| [**setFolderCustomFields**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/set-folder-custom-fields.md) | **PUT** /api/2.0/files/metadata/folder/\{folderId\}/customfields | Set folder custom fields |
| [**setFolderValues**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/set-folder-values.md) | **PUT** /api/2.0/files/metadata/folder/\{folderId\}/values | Set folder metadata values |
| [**unassignFileTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/unassign-file-template.md) | **DELETE** /api/2.0/files/metadata/file/\{fileId\}/templates/\{templateId\} | Unassign a template from a file |
| [**unassignFolderTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/unassign-folder-template.md) | **DELETE** /api/2.0/files/metadata/folder/\{folderId\}/templates/\{templateId\} | Unassign a template from a folder |
| [**updateField**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/update-field.md) | **PUT** /api/2.0/files/metadata/templates/\{templateId\}/fields/\{fieldId\} | Update a metadata field |
| [**updateFolderTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/update-folder-template.md) | **PUT** /api/2.0/files/metadata/folder/\{folderId\}/templates/\{templateId\} | Update a template assignment on a folder |
| [**updateTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/metadata/update-template.md) | **PUT** /api/2.0/files/metadata/templates/\{templateId\} | Update a metadata template |

## Operations

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**abortUploadSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/abort-upload-session.md) | **DELETE** /api/2.0/files/\{folderId\}/session/\{sessionId\} | Abort an upload session |
| [**addFavorites**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/add-favorites.md) | **POST** /api/2.0/files/favorites | Add favorite files and folders |
| [**bulkDownload**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/bulk-download.md) | **PUT** /api/2.0/files/fileops/bulkdownload | Bulk download |
| [**checkConversionStatus**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/check-conversion-status.md) | **GET** /api/2.0/files/file/\{fileId\}/checkconversion | Get conversion status |
| [**checkMoveOrCopyBatchItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/check-move-or-copy-batch-items.md) | **GET** /api/2.0/files/fileops/move | Check move or copy conflicts |
| [**checkMoveOrCopyDestFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/check-move-or-copy-dest-folder.md) | **GET** /api/2.0/files/fileops/checkdestfolder | Check the destination folder |
| [**copyBatchItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/copy-batch-items.md) | **PUT** /api/2.0/files/fileops/copy | Copy files and folders |
| [**createUploadSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/create-upload-session.md) | **POST** /api/2.0/files/\{folderId\}/upload/create_session | Chunked upload |
| [**createUploadSessionInFolder**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/create-upload-session-in-folder.md) | **POST** /api/2.0/files/\{folderId\}/session | Create an upload session |
| [**deleteBatchItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/delete-batch-items.md) | **PUT** /api/2.0/files/fileops/delete | Delete files and folders |
| [**deleteFavoritesFromBody**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/delete-favorites-from-body.md) | **DELETE** /api/2.0/files/favorites | Delete favorite files and folders |
| [**deleteFileVersions**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/delete-file-versions.md) | **PUT** /api/2.0/files/fileops/deleteversion | Delete file versions |
| [**duplicateBatchItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/duplicate-batch-items.md) | **PUT** /api/2.0/files/fileops/duplicate | Duplicate files and folders |
| [**emptyTrash**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/empty-trash.md) | **PUT** /api/2.0/files/fileops/emptytrash | Empty the Trash folder |
| [**finalizeSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/finalize-session.md) | **PUT** /api/2.0/files/\{folderId\}/session/\{sessionId\}/finalize | Finalize an upload session |
| [**getOperationStatuses**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/get-operation-statuses.md) | **GET** /api/2.0/files/fileops | Get active file operations |
| [**getOperationStatusesByType**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/get-operation-statuses-by-type.md) | **GET** /api/2.0/files/fileops/\{operationType\} | Get file operations by type |
| [**markAsRead**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/mark-as-read.md) | **PUT** /api/2.0/files/fileops/markasread | Mark files and folders as read |
| [**moveBatchItems**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/move-batch-items.md) | **PUT** /api/2.0/files/fileops/move | Move files and folders |
| [**startFileConversion**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/start-file-conversion.md) | **PUT** /api/2.0/files/file/\{fileId\}/checkconversion | Start file conversion |
| [**terminateTasks**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/terminate-tasks.md) | **PUT** /api/2.0/files/fileops/terminate/\{id\} | Cancel file operations |
| [**updateFileComment**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/update-file-comment.md) | **PUT** /api/2.0/files/file/\{fileId\}/comment | Update a comment |
| [**uploadAsyncSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/upload-async-session.md) | **POST** /api/2.0/files/\{folderId\}/session/\{sessionId\}/upload | Upload a numbered chunk |
| [**uploadSession**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/operations/upload-session.md) | **POST** /api/2.0/files/\{folderId\}/session/\{sessionId\} | Upload the next chunk |

## Quota

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**resetRoomQuota**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/quota/reset-room-quota.md) | **PUT** /api/2.0/files/rooms/resetquota | Reset the room quota limit |
| [**updateRoomsQuota**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/quota/update-rooms-quota.md) | **PUT** /api/2.0/files/rooms/roomquota | Change the room quota limit |

## Settings

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**changeAccessToThirdparty**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-access-to-thirdparty.md) | **PUT** /api/2.0/files/thirdparty | Change the third-party settings access |
| [**changeAutomaticallyCleanUp**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-automatically-clean-up.md) | **PUT** /api/2.0/files/settings/autocleanup | Update the trash bin auto-clearing setting |
| [**changeDefaultAccessRights**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-default-access-rights.md) | **PUT** /api/2.0/files/settings/dafaultaccessrights | Change the default access rights |
| [**changeDeleteConfirm**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-delete-confirm.md) | **PUT** /api/2.0/files/changedeleteconfrim | Ask for delete confirmation |
| [**changeDownloadZip**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-download-zip.md) | **PUT** /api/2.0/files/settings/downloadtargz | Change the download archive format |
| [**changeExternalSharingSettings**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/change-external-sharing-settings.md) | **PUT** /api/2.0/files/settings/externalsharingsettings | Configure external sharing |
| [**checkDocServiceUrl**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/check-doc-service-url.md) | **PUT** /api/2.0/files/docservice | Set the document service address |
| [**displayFileExtension**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/display-file-extension.md) | **PUT** /api/2.0/files/displayfileextension | Display a file extension |
| [**displayRecent**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/display-recent.md) | **PUT** /api/2.0/files/displayrecent | Show the Recent section |
| [**externalShare**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/external-share.md) | **PUT** /api/2.0/files/settings/external | Change the external sharing ability |
| [**externalShareSocialMedia**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/external-share-social-media.md) | **PUT** /api/2.0/files/settings/externalsocialmedia | Change the external sharing ability on social networks |
| [**forcesave**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/forcesave.md) | **PUT** /api/2.0/files/forcesave | Change the forcesaving ability |
| [**getAutomaticallyCleanUp**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/get-automatically-clean-up.md) | **GET** /api/2.0/files/settings/autocleanup | Get the trash bin auto-clearing setting |
| [**getDefaultTemplates**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/get-default-templates.md) | **GET** /api/2.0/files/settings/defaulttemplate | Get the default template setting |
| [**getDocServiceUrl**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/get-doc-service-url.md) | **GET** /api/2.0/files/docservice | Get the document service address |
| [**getFilesModule**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/get-files-module.md) | **GET** /api/2.0/files/info | Get the Documents module information |
| [**getFilesSettings**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/get-files-settings.md) | **GET** /api/2.0/files/settings | Get file settings |
| [**hideConfirmCancelOperation**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/hide-confirm-cancel-operation.md) | **PUT** /api/2.0/files/hideconfirmcanceloperation | Hide confirmation dialog when canceling operations |
| [**hideConfirmConvert**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/hide-confirm-convert.md) | **PUT** /api/2.0/files/hideconfirmconvert | Hide the confirmation dialog when converting |
| [**hideConfirmRoomLifetime**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/hide-confirm-room-lifetime.md) | **PUT** /api/2.0/files/hideconfirmroomlifetime | Hide confirmation dialog when changing room lifetime settings |
| [**keepNewFileName**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/keep-new-file-name.md) | **PUT** /api/2.0/files/keepnewfilename | Keep the default file name |
| [**resetDefaultTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/reset-default-template.md) | **DELETE** /api/2.0/files/settings/defaulttemplate | Reset the default template setting |
| [**setDefaultTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/set-default-template.md) | **PUT** /api/2.0/files/settings/defaulttemplate | Change the default template setting |
| [**setOpenEditorInSameTab**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/set-open-editor-in-same-tab.md) | **PUT** /api/2.0/files/settings/openeditorinsametab | Open document in the same browser tab |
| [**setOrganizeRoomsGrouping**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/set-organize-rooms-grouping.md) | **PUT** /api/2.0/files/settings/organizegrouping | Organize rooms grouping |
| [**showQuickActions**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/show-quick-actions.md) | **PUT** /api/2.0/files/showquickactions | Display quick actions |
| [**storeForcesave**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/store-forcesave.md) | **PUT** /api/2.0/files/storeforcesave | Change the ability to store the forcesaved files |
| [**storeOriginal**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/store-original.md) | **PUT** /api/2.0/files/storeoriginal | Change the ability to upload original formats |
| [**updateFileIfExist**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/update-file-if-exist.md) | **PUT** /api/2.0/files/updateifexist | Update a file version if it exists |
| [**uploadDefaultTemplate**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/settings/upload-default-template.md) | **POST** /api/2.0/files/settings/defaulttemplate | Upload a file as the default template setting |

## Sharing

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**applyExternalSharePassword**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/apply-external-share-password.md) | **POST** /api/2.0/files/share/\{key\}/password | Unlock a password-protected link |
| [**changeFileOwner**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/change-file-owner.md) | **POST** /api/2.0/files/owner | Change the room or file owner |
| [**getEncryptionAccess**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-encryption-access.md) | **GET** /api/2.0/files/file/\{fileId\}/publickeys | Get file encryption keys |
| [**getExternalShareData**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-external-share-data.md) | **GET** /api/2.0/files/share/\{key\} | Resolve an external share link |
| [**getFileSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-file-security-info.md) | **GET** /api/2.0/files/file/\{id\}/share | Get file sharing rights |
| [**getFolderSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-folder-security-info.md) | **GET** /api/2.0/files/folder/\{id\}/share | Get folder sharing rights |
| [**getGroupsMembersWithFileSecurity**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-groups-members-with-file-security.md) | **GET** /api/2.0/files/file/\{fileId\}/group/\{groupId\}/share | Get file access of group members |
| [**getGroupsMembersWithFolderSecurity**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-groups-members-with-folder-security.md) | **GET** /api/2.0/files/folder/\{folderId\}/group/\{groupId\}/share | Get folder access of group members |
| [**getSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-security-info.md) | **POST** /api/2.0/files/share | Get sharing rights in batch |
| [**getSharedUsers**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/get-shared-users.md) | **GET** /api/2.0/files/file/\{fileId\}/sharedusers | Get users to mention in a file |
| [**removeSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/remove-security-info.md) | **DELETE** /api/2.0/files/share | Remove sharing rights in batch |
| [**sendEditorNotify**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/send-editor-notify.md) | **POST** /api/2.0/files/file/\{fileId\}/sendeditornotify | Notify mentioned users |
| [**setFileSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/set-file-security-info.md) | **PUT** /api/2.0/files/file/\{id\}/share | Share a file |
| [**setFolderSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/set-folder-security-info.md) | **PUT** /api/2.0/files/folder/\{id\}/share | Share a folder |
| [**setSecurityInfo**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/sharing/set-security-info.md) | **PUT** /api/2.0/files/share | Set sharing rights in batch |

## Third-party integration

| Method | HTTP request | Description |
|------------ | ------------- | -------------|
| [**deleteThirdParty**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/delete-third-party.md) | **DELETE** /api/2.0/files/thirdparty/\{providerId\} | Remove a third-party account |
| [**getAllProviders**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/get-all-providers.md) | **GET** /api/2.0/files/thirdparty/providers | Get all third-party providers |
| [**getBackupThirdPartyAccount**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/get-backup-third-party-account.md) | **GET** /api/2.0/files/thirdparty/backup | Get the third-party backup folder |
| [**getCapabilities**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/get-capabilities.md) | **GET** /api/2.0/files/thirdparty/capabilities | Get third-party provider capabilities |
| [**getCommonThirdPartyFolders**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/get-common-third-party-folders.md) | **GET** /api/2.0/files/thirdparty/common | Get common third-party folders |
| [**getThirdPartyAccounts**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/get-third-party-accounts.md) | **GET** /api/2.0/files/thirdparty | Get the third-party accounts |
| [**saveThirdParty**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/save-third-party.md) | **POST** /api/2.0/files/thirdparty | Connect a third-party account |
| [**saveThirdPartyBackup**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/files/third-party-integration/save-third-party-backup.md) | **POST** /api/2.0/files/thirdparty/backup | Connect the third-party backup storage |

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


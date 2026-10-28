# CDocBuilder

Base class used by ONLYOFFICE Document Builder for the document file (document, spreadsheet, presentation, form document, PDF) to be generated.

## Syntax

```cpp
class CDocBuilder
```

## Methods

| Name                                                        | Description                                                                                                                                |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| [CloseFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/CloseFile.md)                                   | Closes the file to stop working with it.                                                                                                   |
| [CreateFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/CreateFile.md)                                 | Creates a new file.                                                                                                                        |
| [CreateInstance](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/CreateInstance.md)                         | Creates an instance of the CDocBuilder class. *(COM only)*                                                                                 |
| [Dispose](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/Dispose.md)                                       | Unloads the ONLYOFFICE Document Builder from the application memory when it is no longer needed. *(not used in .Net)*                      |
| [Destroy](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/Destroy.md)                                       | Unloads the ONLYOFFICE Document Builder from the application memory when it is no longer needed. *(.Net only)*                             |
| [Execute](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/Execute.md)                                       | Executes the command and returns the [CDocBuilderValue](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderValue.md). *(COM only)*                             |
| [ExecuteCommand](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/ExecuteCommand.md)                         | Executes the command which will be used to create the document file (document, spreadsheet, presentation, form document, PDF).        |
| [GetContext](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/GetContext.md)                                 | Returns the current JS context.                                                                                                            |
| [GetVersion](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/GetVersion.md)                                 | Returns the ONLYOFFICE Document Builder engine version. *(not used in COM)*                                                                |
| [Initialize](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/Initialize.md)                                 | Initializes the ONLYOFFICE Document Builder as a library for the application to be able to work with it.                                   |
| [IsSaveWithDoctrendererMode](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/IsSaveWithDoctrendererMode.md) | Specifies if the doctrenderer mode is used when building a document or getting content from the editor when saving a file.                 |
| [OpenFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/OpenFile.md)                                     | Opens the document file which will be edited and saved afterwards.                                                                         |
| [Run](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/Run.md)                                               | Runs the ONLYOFFICE Document Builder executable.                                                                                           |
| [RunText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/RunText.md)                                       | Runs all the commands for the document creation using a single command. *(not used in C++)*                                                |
| [RunTextA](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/RunTextA.md)                                     | Runs all the commands for the document creation using a single command in the UTF8 format. *(C++ only)*                                    |
| [RunTextW](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/RunTextW.md)                                     | Runs all the commands for the document creation using a single command in the Unicode format. *(C++ only)*                                 |
| [SaveFile](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/SaveFile.md)                                     | Saves the file after all the changes are made.                                                                                             |
| [SetProperty](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/SetProperty.md)                               | Sets an argument which can be transferred to the program outside the CDocBuilder.ExecuteCommand method.                                    |
| [SetPropertyW](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/SetPropertyW.md)                             | Sets an argument in the Unicode format which can be transferred to the program outside the CDocBuilder.ExecuteCommand method. *(C++ only)* |
| [SetTmpFolder](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/SetTmpFolder.md)                             | Sets the path to the folder where the program will temporarily save files needed for the program correct work.                             |
| [WriteData](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilder/WriteData.md)                                   | Writes data to the log file.                                                                                                               |

:::note
**Java** uses camelCase method names: `closeFile`, `createFile`, `executeCommand`, etc.
:::

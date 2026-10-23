# CDocBuilderContext

Class used by ONLYOFFICE Document Builder for getting JS context for working.

## Syntax

```cpp
class CDocBuilderContext
```

## Methods

| Name                                              | Description                                                                |
| ------------------------------------------------- | -------------------------------------------------------------------------- |
| [AllocMemoryTypedArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/AllocMemoryTypedArray.md) | Allocates the memory for a typed array. *(C++ only)*                       |
| [CreateArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateArray.md)                     | Creates an array, an analogue of `new Array (length)` in JS.               |
| [CreateNull](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateNull.md)                       | Creates a null value, an analogue of `null` in JS.                         |
| [CreateObject](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateObject.md)                   | Creates an empty object, an analogue of `{}` in JS.                        |
| [CreateScope](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateScope.md)                     | Creates a context scope.                                                   |
| [CreateTypedArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateTypedArray.md)           | Creates a Uint8Array value, an analogue of `Uint8Array` in JS. *(not used in Java and Python)* |
| [CreateUndefined](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/CreateUndefined.md)             | Creates an undefined value, an analogue of `undefined` in JS.              |
| [FreeMemoryTypedArray](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/FreeMemoryTypedArray.md)   | Frees the memory for a typed array. *(C++ only)*                           |
| [GetGlobal](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/GetGlobal.md)                         | Returns the global object for the current context.                         |
| [IsError](https://api.onlyoffice.com/ai-plugin-docs-update/docs/document-builder/builder-framework/CDocBuilderContext/IsError.md)                             | Checks for errors in JS.                                                   |

:::note
**Java** uses camelCase method names: `createArray`, `createNull`, `createObject`, etc.
:::

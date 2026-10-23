---
custom_edit_url: https://github.com/ONLYOFFICE/docspace-plugin-sdk/blob/master/src/interfaces/components/ILink.ts
---

# ILink

Defines the link component properties.

![link](https://api.onlyoffice.com/assets/images/docspace/link.png#gh-light-mode-only)![link](https://api.onlyoffice.com/assets/images/docspace/link.dark.png#gh-dark-mode-only)

## Example

```typescript
import { ILink, LinkType, LinkTarget } from "@onlyoffice/docspace-plugin-sdk";

const link: ILink = {
  href: "https://example.com",
  text: "Visit Example",
  type: LinkType.page,
  target: LinkTarget.blank,
  isBold: false,
  color: "accent",
  fontSize: "14px",
  onClick: () => {
    console.log("Link clicked");
  }
};
```

## Extends

- [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md)

## Properties

import APITable from '@site/src/components/APITable/APITable';

<APITable>

| Property | Type | Description | Inherited from |
| ------ | ------ | ------ | ------ |
| `href?` | `string` | URL for the link | - |
| `id?` | `string` | Link identifier | - |
| `isHovered?` | `boolean` | Sets hovered state and link effects | - |
| `isTextOverflow?` | `boolean` | Activates text-overflow with ellipsis | - |
| `noHover?` | `boolean` | Disables hover effect | - |
| `enableUserSelect?` | `boolean` | Enables user selection | - |
| `type?` | [`LinkType`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/ILink.md#linktype) | Link type (page or action) | - |
| `target?` | [`LinkTarget`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/ILink.md#linktarget) | Target attribute for link | - |
| `textDecoration?` | \| `"none"` \| `"line-through"` \| `"overline"` \| `"underline"` \| `"underline dotted"` \| `"underline dashed"` | Text decoration style | - |
| `onClick?` | () => [`TReturnMessage`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/utils.md#treturnmessage) | Click handler (for action type links) | - |
| `text` | `string` | Defines the text | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`text`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#text) |
| `title?` | `string` | Defines the text title | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`title`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#title?) |
| `fontSize?` | `string` | Defines the text font size | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`fontSize`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#fontSize?) |
| `fontWeight?` | `string` \| `number` | Defines the text font weight | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`fontWeight`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#fontWeight?) |
| `truncate?` | `boolean` | Specifies whether the word wrapping is set | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`truncate`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#truncate?) |
| `isBold?` | `boolean` | Specifies whether the text font weight is set to bold | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`isBold`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#isBold?) |
| `isItalic?` | `boolean` | Specifies whether the text style is set to italic | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`isItalic`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#isItalic?) |
| `isInline?` | `boolean` | Specifies whether the "display: inline-block" property is set | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`isInline`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#isInline?) |
| `textAlign?` | `string` | Specifies whether the "text-align" property is set | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`textAlign`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#textAlign?) |
| `noSelect?` | `boolean` | Specifies whether the text selection is disabled | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`noSelect`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#noSelect?) |
| `display?` | `string` | Specifies whether the "display" property is set | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`display`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#display?) |
| `lineHeight?` | `string` | Defines the text line height | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`lineHeight`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#lineHeight?) |
| `color?` | `string` | Defines the text color | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`color`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#color?) |
| `className?` | `string` | Defines the CSS class for styling the component. Can be used to override or extend the default component styles. | [`IText`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md).[`className`](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components/IText.md#className?) |

</APITable>

## LinkType

Defines the link type.

### Enumeration Members

#### page

```ts
page: "page";
```

Regular page link

#### action

```ts
action: "action";
```

Action link (clickable but not navigating)

***

## LinkTarget

Defines the link target attribute.

### Enumeration Members

#### blank

```ts
blank: "_blank";
```

Opens in a new tab

#### self

```ts
self: "_self";
```

Opens in the same frame

#### parent

```ts
parent: "_parent";
```

Opens in the parent frame

#### top

```ts
top: "_top";
```

Opens in the full body of the window


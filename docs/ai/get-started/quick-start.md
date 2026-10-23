---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Quick start

Add an AI-generated comment or footnote to selected text using the ONLYOFFICE AI agent.

**Time**: 30 minutes | **Skill level**: Advanced

## Step 1: Set up your environment

1. Clone the [onlyoffice.github.io](https://github.com/ONLYOFFICE/onlyoffice.github.io) repository to your local machine.
2. Navigate to the helpers folder: `sdkjs-plugins/content/ai/.dev/helpers/` and open a folder for the targeted editor: **word**, **cell** or **slide**.
3. Create a new file for your function, for example `commentText.js`.
4. Make sure that code is wrapped in an `IIFE function`.

## Step 2: Register the function

Use the `RegisteredFunction` object to define the function's name, expected parameters, and examples that teach the AI model when and how to call it:

```javascript
let func = new RegisteredFunction({
  name: "commentText",
  description: "Use this function if you are asked to comment or explain anything.",
  parameters: {
    type: "object",
    properties: {
      prompt: {
        type: "string",
        description: "The instruction for what to explain or comment about the text.",
      },
      type: {
        type: "string",
        enum: ["comment", "footnote"],
        description: "Whether to add as a comment or as a footnote.",
        default: "comment",
      },
    },
    required: ["prompt"],
  },
  examples: [
    {
      prompt: "Explain this text",
      arguments: { prompt: "Explain this text", type: "comment" },
    },
    {
      prompt: "Add a footnote to selected text",
      arguments: { prompt: "Add a footnote to this text", type: "footnote" },
    },
    {
      prompt: "Comment on this text",
      arguments: { prompt: "Comment this text" },
    },
  ],
});
```

**Key fields explained**:

- `name` - The function name the AI model will invoke
- `parameters` - Parameters the function expects from the AI as a JSON object
- `examples` - Sample invocations that teach the AI the correct calling syntax
- `description` - Tells the AI what the function does and when to use it

## Step 3: Retrieve the selected text

Inside `func.call`, use `Asc.Editor.callCommand()` to read the currently selected text from the document:

```javascript
func.call = async function (params) {
  let text = await Asc.Editor.callCommand(function () {
    let doc = Api.GetDocument();
    let range = doc.GetRangeBySelect();
    let text = range ? range.GetText() : "";
    if (!text) {
      text = doc.GetCurrentWord();
      doc.SelectCurrentWord();
    }
    return text;
  });
```

## Step 4: Build the prompt and initialize the request engine

Combine the user's instruction with the retrieved text, then create a request engine to communicate with the AI model:

```javascript
  let argPrompt = params.prompt + ":\n" + text;

  let requestEngine = await AI.Request.create(AI.ActionType.Chat);
  if (!requestEngine) return;
```

## Step 5: Send the request and apply the result

Send the prompt to the AI model and insert its response into the document as a comment or footnote.

:::info Asc.scope
`Asc.scope` is a shared object used to pass data into `callCommand` closures. Because `callCommand` runs in a separate context, local variables are not directly accessible inside it - `Asc.scope` bridges the two contexts.
:::

To insert as a comment:

```javascript
  // Insert as a comment
  let result = await requestEngine.chatRequest(argPrompt, false);
  if (!result) return;

  Asc.scope.data = result;
  Asc.scope.model = requestEngine.modelUI.name;
  await Asc.Editor.callCommand(function () {
    let range = Api.GetDocument().GetRangeBySelect();
    let comment = range.AddComment(
      Asc.scope.data,
      Asc.scope.model,
      "uid" + Asc.scope.model,
    );
    Api.GetDocument().ShowComment([comment.GetId()]);
  });
```

To insert as a footnote instead:

```javascript
  // Insert as a footnote
  let result = await requestEngine.chatRequest(argPrompt, false);
  if (!result) return;

  await Asc.Editor.callCommand(function () {
    Api.GetDocument().AddFootnote();
  });
  await Asc.Library.PasteText(result);
```

:::tip
Wrap document changes in [`StartAction`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/StartAction.md) / [`EndAction`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/EndAction.md) so the whole operation can be undone as a single step. See the [`commentText`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/custom-ai-tools.md#code-example) example for the full pattern.
:::

## Step 6: Build and load custom AI tool

1. Run `helpers.py` in `sdkjs-plugins/content/ai/.dev/helpers/` to regenerate `helpers.js` in the cloned repository, at `sdkjs-plugins/content/ai/scripts/helpers/`.

:::warning Important
Desktop Editors **10.0.0** and later load custom AI tools from the `addon\sdkjs-plugins` folder.

Plugin Manager does not list AI Tools, and the custom store URL does not update it. Everything needs to be done manually.

To restore the default tools, replace the generated file with the backup file or [repair Desktop Editor](https://helpcenter.onlyoffice.com/desktop/installation/desktop-online-installer.aspx) with the online installer (**Update/Repair**). Enable **Clear cached data** if Chat still loads your custom `helpers.js`.
:::

2. Copy the generated `helpers.js` to the following folder:

<Tabs>
  <TabItem value="win" label="Windows">

```bash
%LOCALAPPDATA%\ONLYOFFICE\DesktopEditors\data\addon\sdkjs-plugins\{9DC93CDB-B576-4F0C-B55E-FCC9C48DD007}\scripts\helpers\
```

  </TabItem>
  <TabItem value="mac" label="macOS">

```bash
~/Library/Application Support/asc.onlyoffice.ONLYOFFICE/data/addon/sdkjs-plugins/{9DC93CDB-B576-4F0C-B55E-FCC9C48DD007}/scripts/helpers/
```

  </TabItem>
  <TabItem value="lin" label="Linux">

```bash
~/.local/share/onlyoffice/desktopeditors/addon/sdkjs-plugins/{9DC93CDB-B576-4F0C-B55E-FCC9C48DD007}/scripts/helpers/
```

  </TabItem>
</Tabs>

3. **Restart** ONLYOFFICE Desktop Editor.

## Step 7: Test your custom AI tool

1. Open a document and select some text.
2. Open the AI agent dialog (`Ctrl + /`).
3. Type `Explain this text` and press **Enter**.
4. The AI agent inserts a comment with an AI-generated explanation of the selected text.

    ![Comment text](https://api.onlyoffice.com/assets/images/plugins/comment-text.png#gh-light-mode-only)![Comment Text](https://api.onlyoffice.com/assets/images/plugins/comment-text.dark.png#gh-dark-mode-only)

5. More information about the called tool is available in the AI Chat.

    ![Custom tool call](https://api.onlyoffice.com/assets/images/plugins/custom-tool-call.png#gh-light-mode-only)![Custom tool call](https://api.onlyoffice.com/assets/images/plugins/custom-tool-call.dark.png#gh-dark-mode-only)

## Next steps

**Learn more**:

- [Getting started with ONLYOFFICE AI agent](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/ai-agent.md)
- [Learn more about custom AI tools](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/custom-ai-tools.md)
- [Text annotations API guide](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/text-annotations-guide.md)

**Explore examples**:

- [Browse all AI tool examples](https://api.onlyoffice.com/samples/?doctype=ai&text=ai+tools)

**Need help?**

- [Developer Forum](https://community.onlyoffice.com/) - Community support
- [GitHub Issues](https://github.com/ONLYOFFICE/sdkjs-plugins) - Report bugs
- [FAQ](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/more-information/faq.md) - Frequently asked questions

---
sidebar_position: 5
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Custom AI tools (beta)

Custom AI tools are functions that define the functionality of the AI agent. They specify:

- what request to send to the AI model;
- what manipulations to perform on the document.

Adding custom AI tools expands the AI agent's capabilities and allows adapting it to specific use cases. Whether working with documents, spreadsheets, or presentations, custom AI tools let you integrate AI-driven operations directly into your workflow and align the agent's behavior with your requirements.

You can find ready-to-use custom AI tools [here](https://api.onlyoffice.com/samples/?doctype=ai&text=ai+tools) or create your own ones.

:::warning Current limitation
Adding a custom AI tool requires modifying the [AI Tools source](https://github.com/ONLYOFFICE/onlyoffice.github.io/tree/master/sdkjs-plugins/content/ai) directly. On Desktop Editors 10.0.0 and later, AI Tools is already installed as a core addon. See [Installing](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/ai-plugin.md#installing) and [Setup](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/custom-ai-tools.md#setup) for more information.
:::

## How it works {#usage}

Custom AI tool calling in the ONLYOFFICE AI agent follows a flow similar to [function calling in LLM APIs](https://platform.openai.com/docs/guides/function-calling):

1. **Function registration.** Each function is registered with a name, parameter list, description, and usage examples. This metadata tells the AI model what the function does and when to invoke it.
2. **User prompt.** The user opens the AI agent and types a request.
3. **Function selection.** The AI model examines the prompt and the list of available functions, then decides which function to call and with what arguments.
4. **Execution.** The selected function runs: it sends a request to the AI model and applies the result to the document using the [Office API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/get-started/overview.md).

## Setup {#setup}

To add a custom AI tool and make it available in the AI agent:

1. Clone the [onlyoffice.github.io](https://github.com/ONLYOFFICE/onlyoffice.github.io) repository to your local machine.
2. Write your function in the helpers folder (`sdkjs-plugins/content/ai/.dev/helpers`). Depending on the editor type, place it in the `cell/`, `slide/`, or `word/` folder (see [Function registration](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/custom-ai-tools.md#registration) below).
3. Run `helpers.py` in `sdkjs-plugins/content/ai/.dev/helpers/` to regenerate `helpers.js` in the cloned repository, at `sdkjs-plugins/content/ai/scripts/helpers/`.
4. Copy the generated `helpers.js` to the following folder:

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

5. **Restart** ONLYOFFICE Desktop Editor.

## Example: the commentText function {#example}

The `commentText` function allows adding AI-generated comments directly to the document. Here’s how it works:

1. Make sure AI Tools is [available](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/ai-plugin.md#installing) and [set up correctly](https://api.onlyoffice.com/ai-plugin-docs-update/docs/ai/guides/ai-plugin.md#configuring).
2. Select a word to leave a comment on.
3. Open the AI agent dialog box (`CTRL + /`).
4. Type in the instruction for the AI agent. For example: `Explain this text` or `Add a footnote to this text`.
5. Press `Enter`.

![commentText execution](https://api.onlyoffice.com/assets/images/plugins/comment-text-function.png#gh-light-mode-only)![commentText execution](https://api.onlyoffice.com/assets/images/plugins/comment-text-function.dark.png#gh-dark-mode-only)

The AI agent will run the `commentText` function and insert relevant comments into the document.

![commentText result](https://api.onlyoffice.com/assets/images/plugins/comment-text-result.png#gh-light-mode-only)![commentText result](https://api.onlyoffice.com/assets/images/plugins/comment-text-result.dark.png#gh-dark-mode-only)

## How to create custom AI tools {#creating-ai-tools}

The process of making a custom AI tool involves two main phases:

- **Function registration**: Registers the AI function and its metadata within the agent's environment.
- **Function execution**: Implements the core logic, which includes sending requests to the AI model and manipulating document content using our [Office API](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/get-started/overview.md).

### Function registration {#registration}

To add a new function, the `RegisteredFunction` object is used, which adds metadata and logic of the custom function to the AI agent.

#### Parameters {#parameters}

| Name        | Type             | Example                                                                                          | Description                                                                      |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| name        | string           | `"commentText"`                                                                                  | The function name.                                                               |
| parameters  | object           | `{ type: "object", properties: { prompt: { type: "string" } }, required: ["prompt"] }`           | An object describing the parameters the function expects from the AI.            |
| examples    | object[] | `[{ prompt: "Explain this text", arguments: { prompt: "Explain this text", type: "comment" } }]` | The examples of correct function calls for the AI.                               |
| description | string           | `"Adds a comment or footnote to explain or annotate the selected text."`                         | The function description which explains to the AI what the function is used for. |

These parameters are used by the AI. The `RegisteredFunction()` object is defined in the [helperFuncs.js](https://github.com/ONLYOFFICE/onlyoffice.github.io/blob/master/sdkjs-plugins/content/ai/scripts/helpers/helperFuncs.js) file.

### Example {#code-example}

The full function flow is shown below, with inline comments explaining each step:

```js
(function () {
  // Registers the "commentText" tool for the AI agent.
  // The metadata below (name/description/parameters/examples) is used by the model
  // to decide when and how to call this tool.
  let func = new RegisteredFunction({
    name: "commentText",
    description:
      "Adds a comment or footnote to explain or annotate the selected text. If no text is selected, works with the current paragraph.",
    parameters: {
      type: "object",
      properties: {
        // The instruction for the AI model (e.g., "Explain this text").
        prompt: {
          type: "string",
          description:
            "The instruction for what to explain or comment about the text.",
        },
        // Determines how the response will be inserted into the document.
        // Default behavior is a comment.
        type: {
          type: "string",
          enum: ["comment", "footnote"],
          description: "Whether to add as a comment or as a footnote.",
          default: "comment",
        },
      },
      required: ["prompt"],
    },
    // Example calls that teach the model the correct JSON arguments to provide.
    examples: [
      {
        prompt: "Explain this text",
        arguments: { prompt: "Explain this text", type: "comment" },
      },
      {
        prompt: "Add a historical context as footnote",
        arguments: { prompt: "Add historical context", type: "footnote" },
      },
      {
        prompt: "Comment on the significance",
        arguments: { prompt: "Explain significance", type: "comment" },
      },
    ],
  });

  // The actual logic that runs when the AI agent calls "commentText".
  func.call = async function (params) {
    // Decide whether we insert as a comment or as a footnote.
    let type = params.type;
    let isFootnote = "footnote" === type;

    // 1) Read selected text or document text for the model.
    let text = ((await Asc.Library.GetSelectedText()) || "").trim();
    if (!text) {
      // callCommand runs inside the document context, where Api is available.
      text = await Asc.Editor.callCommand(function () {
        let doc = Api.GetDocument();
        let range = doc.GetRangeBySelect();
        let t = range ? range.GetText() : "";
        if (!t) {
          // No selection: use the paragraph under the cursor and select it
          // so the later insert still has a range to attach to.
          let para = doc.GetCurrentParagraph();
          if (para) {
            t = para.GetText();
            let paraRange = para.GetRange();
            if (paraRange) paraRange.Select();
          }
        }
        if (!t) {
          // Last fallback: the word at the cursor.
          t = doc.GetCurrentWord();
          doc.SelectCurrentWord();
        }
        return t;
      });
    }
    if (!text) {
      throw new Error(
        "Select some text in the document first, then run the command again.",
      );
    }

    // 2) Combine the user instruction with the document text for the model.
    let argPrompt = params.prompt + ":\n" + text;

    // 3) Desktop 10: AI.Request.create is async. Without await, chatRequest is missing.
    let requestEngine = await AI.Request.create(AI.ActionType.Chat);
    if (!requestEngine) return;

    let actionName = "AI (" + requestEngine.modelUI.name + ")";
    let result = "";
    // Block = progress lock while the model runs. Do not wrap the document
    // edit in the same block: EndAction("Block") can roll back nested groups.
    await Editor.StartAction("Block", actionName);
    try {
      // Second argument false = wait for the full reply. A stream callback
      // would insert one comment/footnote per delta chunk.
      result = await requestEngine.chatRequest(argPrompt, false);
    } finally {
      await Editor.EndAction("Block", actionName);
    }
    if (!result) {
      throw new Error("The AI model returned an empty response.");
    }

    // callCommand cannot close over outer locals. Pass values through Asc.scope.
    Asc.scope.data = result;
    Asc.scope.model = requestEngine.modelUI.name;

    // GroupActions = one undo step for the insert. Must start after Block ends.
    await Editor.StartGroupActions();
    try {
      if (isFootnote) {
        // AddFootnote at the current selection, then write into the new footnote body.
        let footnoteText = await Asc.Editor.callCommand(function () {
          let doc = Api.GetDocument();
          let range = doc.GetRangeBySelect();
          if (!range || !range.GetText()) {
            // After sending from Chat, the document range is often gone.
            // Use the paragraph under the cursor so AddFootnote has an anchor.
            let para = doc.GetCurrentParagraph();
            if (para) range = para.GetRange();
            if (range) range.Select();
          }
          doc.AddFootnote();
          // First paragraphs of every footnote. The last one is the one we just added.
          let footnotes = doc.GetFootnotesFirstParagraphs();
          if (!footnotes || !footnotes.length) return "";
          let paragraph = footnotes[footnotes.length - 1];
          paragraph.AddText(Asc.scope.data);
          // Return the written text so the caller can tell insert succeeded.
          return paragraph.GetText();
        });
        if (!footnoteText) {
          throw new Error(
            "Could not add a footnote. Click in the document paragraph first.",
          );
        }
      } else {
        // Attach a review comment to the selected range and open the comment pane.
        let commentId = await Asc.Editor.callCommand(function () {
          let doc = Api.GetDocument();
          let range = doc.GetRangeBySelect();
          if (!range || !range.GetText()) {
            let para = doc.GetCurrentParagraph();
            if (para) range = para.GetRange();
          }
          if (!range) return null;
          // AddComment(text, author name, author id).
          let comment = range.AddComment(
            Asc.scope.data,
            Asc.scope.model,
            "uid" + Asc.scope.model,
          );
          if (!comment) return null;
          doc.ShowComment([comment.GetId()]);
          // Comment id is the success signal, same idea as footnote GetText().
          return comment.GetId();
        });
        if (!commentId) {
          throw new Error(
            "Could not add a comment. Select text in the document first.",
          );
        }
      }
    } finally {
      await Editor.EndGroupActions();
    }
  };

  return func;
})();
```

:::note
To ensure the entire block of changes can be rolled back after the request is executed, the `commentText` function uses [`StartAction`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/StartAction.md) and [`EndAction`](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/EndAction.md). `"Block"` wraps the model request (`Editor.StartAction` / `Editor.EndAction`). `"GroupActions"` wraps the document edit (`Editor.StartGroupActions` / `Editor.EndGroupActions`).
:::

The AI agent functionality continues to evolve alongside the needs of today's digital world. Extend its capabilities by creating your own custom tools, tailored to your specific use cases.

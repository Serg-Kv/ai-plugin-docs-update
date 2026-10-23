---
hide_table_of_contents: true
description: Add a comment to the selected text.
tags: ["Docs", "Plugins", "AI Tools", "Documents"]
---

import Video from '@site/src/components/Video/Video';

# Comment text

This function adds an explanation or comment to the text. If no text or paragraph number is specified, the current paragraph is used by default. Specify whether the explanation should be added as a comment or as a footnote. The AI will generate the content based on your prompt and insert it in the chosen format.

## Prompts

- Explain this text
- Add a footnote to this text
- Comment this text

## Function registration {#function-registration}

```ts
let func = new RegisteredFunction({
    name: "commentText",
    description:
        "Use this function if you asked to comment or explain anything. If text or paragraph number is not specified assume that we are working with the current paragraph. Specify whether the explanation should be added as a comment or as a footnote. The AI will generate the content based on your prompt and insert it in the chosen format.",
    parameters: {
        type: "object",
        properties: {
            type: {
                type: "string",
                description:
                    "Whether to add as a 'comment' or as a 'footnote' (default is 'comment')",
            },
        },
        required: ["type"],
    },
    examples: [
        {
            prompt: "Explain this text",
            arguments: { type: "comment" },
        },
        {
            prompt: "Add a footnote to this text",
            arguments: { type: "footnote" },
        },
        {
            prompt: "Comment this text",
            arguments: { type: "comment" },
        },
        {
            prompt: "Explain this text as a footnote",
            arguments: { type: "footnote" },
        },
        {
            prompt: "Explain selected text as a comment",
            arguments: { type: "comment" },
        },
    ],
});
```

### Parameters

| Name | Type   | Example   | Description                                                                                                |
|------|--------|-----------|------------------------------------------------------------------------------------------------------------|
| type | string | "comment" | Specifies whether to add an explanation as a "comment" or as a "footnote". The default value is "comment". |

## Function execution {#function-execution}

```ts
(function () {
    let func = new RegisteredFunction({
        name: "commentText",
        description:
            "Use this function if you asked to comment or explain anything. If text or paragraph number is not specified assume that we are working with the current paragraph. Specify whether the explanation should be added as a comment or as a footnote. The AI will generate the content based on your prompt and insert it in the chosen format.",
        parameters: {
            type: "object",
            properties: {
                type: {
                    type: "string",
                    description:
                        "Whether to add as a 'comment' or as a 'footnote' (default is 'comment')",
                },
            },
            required: ["type"],
        },
        examples: [
            {
                prompt: "Explain this text",
                arguments: { type: "comment" },
            },
            {
                prompt: "Add a footnote to this text",
                arguments: { type: "footnote" },
            },
            {
                prompt: "Comment this text",
                arguments: { type: "comment" },
            },
            {
                prompt: "Explain this text as a footnote",
                arguments: { type: "footnote" },
            },
            {
                prompt: "Explain selected text as a comment",
                arguments: { type: "comment" },
            },
        ],
    });

    func.call = async function (params) {
        let type = params.type;
        let isFootnote = "footnote" === type;

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

        let argPrompt = params.prompt + ":\n" + text;

        let requestEngine = await AI.Request.create(AI.ActionType.Chat);
        if (!requestEngine) return;

        await Asc.Editor.callMethod("StartAction", [
            "Block",
            "AI (" + requestEngine.modelUI.name + ")",
        ]);
        await Asc.Editor.callMethod("StartAction", ["GroupActions"]);

        let result = await requestEngine.chatRequest(argPrompt, false);
        if (result) {
            Asc.scope.data = result;
            Asc.scope.model = requestEngine.modelUI.name;

            if (isFootnote) {
                await Asc.Editor.callCommand(function () {
                    Api.GetDocument().AddFootnote();
                });
                await Asc.Library.PasteText(result);
            } else {
                await Asc.Editor.callCommand(function () {
                    let doc = Api.GetDocument();
                    let range = doc.GetRangeBySelect();
                    if (!range) return;

                    let comment = range.AddComment(
                        Asc.scope.data,
                        Asc.scope.model,
                        "uid" + Asc.scope.model,
                    );
                    if (!comment) return;
                    doc.ShowComment([comment.GetId()]);
                });
            }
        }

        await Asc.Editor.callMethod("EndAction", [
            "Block",
            "AI (" + requestEngine.modelUI.name + ")",
        ]);
        await Asc.Editor.callMethod("EndAction", ["GroupActions"]);
    };

    return func;
})();
```

Methods used: [GetDocument](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/Api/Methods/GetDocument.md), [GetRangeBySelect](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetRangeBySelect.md), [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/GetText.md), [AddComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiRange/Methods/AddComment.md), [GetCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/GetCurrentWord.md), [SelectCurrentWord](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/SelectCurrentWord.md), [AddFootnote](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/AddFootnote.md), [ShowComment](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiDocument/Methods/ShowComment.md), [GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/document-api/ApiComment/Methods/GetId.md), [EndAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/EndAction.md), [StartAction](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/document-api/Methods/StartAction.md), [Asc.scope object](https://api.onlyoffice.com/ai-plugin-docs-update/docs/plugins/interacting-with-editors/overview/how-to-call-commands.md#ascscope-object)

## Result

<Video src="https://api.onlyoffice.com/assets/images/plugins/functions-video/document-editor/comment-text" dark />

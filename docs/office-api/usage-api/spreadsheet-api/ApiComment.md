# ApiComment

Class representing a comment.

## Properties

| Name | Type | Description |
| ---- | ---- | ----------- |
| AuthorName | string | Returns or sets the comment author's name. |
| Id | string | Returns the current comment ID. |
| QuoteText | string | Returns the quote text of the current comment. |
| RepliesCount | Number | Returns a number of the comment replies. |
| Solved | boolean | Checks if a comment is solved or not or marks a comment as solved. |
| Text | string | Returns or sets the comment text. |
| Time | number \| string | Returns or sets the timestamp of the comment creation in the current time zone format. |
| TimeUTC | number \| string | Returns or sets the timestamp of the comment creation in UTC format. |
| UserId | string | Returns or sets the user ID of the comment author. |

## Methods

The following table lists the available methods.

| Method | Returns | Description |
| ------ | ------- | ----------- |
| [AddReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/AddReply.md) | None | Adds a reply to a comment. |
| [Delete](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/Delete.md) | boolean | Deletes the ApiComment object. |
| [GetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetAuthorName.md) | string | Returns the comment author's name. |
| [GetClassType](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetClassType.md) | "comment" | Returns a type of the ApiComment class. |
| [GetId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetId.md) | string | Returns the current comment ID. |
| [GetQuoteText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetQuoteText.md) | String \| null | Returns the quote text of the current comment. |
| [GetRepliesCount](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetRepliesCount.md) | Number \| null \| undefined | Returns a number of the comment replies. |
| [GetReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetReply.md) | [ApiCommentReply](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiCommentReply.md) \| null \| undefined | Returns the specified comment reply. |
| [GetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetText.md) | string | Returns the comment text. |
| [GetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetTime.md) | Number | Returns the timestamp of the comment creation in the current time zone format. |
| [GetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetTimeUTC.md) | Number | Returns the timestamp of the comment creation in UTC format. |
| [GetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/GetUserId.md) | string | Returns the user ID of the comment author. |
| [IsSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/IsSolved.md) | boolean | Checks if a comment is solved or not. |
| [RemoveReplies](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/RemoveReplies.md) | None | Removes the specified comment replies. |
| [SetAuthorName](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetAuthorName.md) | None | Sets the comment author's name. |
| [SetSolved](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetSolved.md) | None | Marks a comment as solved. |
| [SetText](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetText.md) | None | Sets the comment text. |
| [SetTime](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetTime.md) | None | Sets the timestamp of the comment creation in the current time zone format. |
| [SetTimeUTC](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetTimeUTC.md) | None | Sets the timestamp of the comment creation in UTC format. |
| [SetUserId](https://api.onlyoffice.com/ai-plugin-docs-update/docs/office-api/usage-api/spreadsheet-api/ApiComment/Methods/SetUserId.md) | None | Sets the user ID to the comment author. |

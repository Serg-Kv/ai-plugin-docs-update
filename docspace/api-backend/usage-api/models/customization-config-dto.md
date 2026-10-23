# CustomizationConfigDto
How the editor interface is dressed: branding, the buttons that lead back into the portal, and the behaviour of review, mentions and form submission.

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
| **about** | **Boolean** | Whether the About entry of the editor menu is shown. | [optional] [example: `true`] |
| **customer** | [**CustomerConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/customer-config-dto.md) | The branding of the organization running the portal. It is filled in on a server installation only and is empty in the cloud. | [optional] |
| **anonymous** | [**AnonymousConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/anonymous-config-dto.md) | How an anonymous participant is treated in this session. | [optional] |
| **feedback** | [**FeedbackConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/feedback-config-dto.md) | The support link the editor offers behind its feedback button. | [optional] |
| **forcesave** | **Boolean** | Whether the editors write intermediate revisions while the document stays open. It is empty when the portal leaves the decision to the editors themselves. | [optional] [example: `false`] [nullable] |
| **goback** | [**GobackConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/goback-config-dto.md) | Where the editor returns the user to when they leave the document. It is empty when there is nowhere to go back to, as in an embedded opening. | [optional] |
| **review** | [**ReviewConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/review-config-dto.md) | How tracked changes are displayed when the document opens; it depends on whether this session may write. | [optional] |
| **logo** | [**LogoConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/logo-config-dto.md) | The logo the editor shows, in the variants the current layout and file type need. | [optional] |
| **mentionShare** | **Boolean** | Whether mentioning a user who cannot yet open the document offers to share it with them, instead of silently notifying nobody. | [optional] [example: `true`] |
| **submitForm** | [**SubmitFormDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/submit-form-dto.md) | The submit button of a form: whether it is shown and what it says. | [optional] |
| **startFillingForm** | [**StartFillingForm**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/start-filling-form.md) | The button that starts filling out the form. It is empty when this opening offers no such button. | [optional] |
| **ai** | [**AiConfigDto**](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/api-backend/usage-api/models/ai-config-dto.md) | The AI configuration settings. | [optional] |

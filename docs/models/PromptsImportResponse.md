# LLMPulse.SDK.Model.PromptsImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**ProcessedRows** | **int** | Distinct rows imported or matched to an existing prompt | 
**Created** | **int** |  | 
**Duplicates** | **int** | Rows that matched an existing prompt (they still get the row&#39;s tags, unless a team member lacks update access to Prompts) | 
**Tagged** | **int** | New prompt-tag links | 
**CreatedTags** | **int** |  | 
**RowErrors** | [**List&lt;PromptsImportResponseRowErrorsInner&gt;**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped or whose tags were not added, by their index in rows | 
**Tracked** | **bool** | Whether scheduled runs include the project the prompts were imported into. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes | 
**RequestId** | **string** |  | 
**LengthWarning** | **string** | Which tracked AI models will skip new prompts that are too long for them | 
**PromptsAvailable** | **int** | Prompt slots left on the plan; null when unlimited | 
**UntrackedReason** | **string** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked | 
**Warning** | **string** | What to do when tracked is false, or why some first runs wait when first_runs_wait_until is set. Null otherwise | 
**FirstRunsWaitUntil** | **DateTime** | Set when the account&#39;s allowance of AI answers left this cycle, or the project&#39;s own share of it when the account caps each project&#39;s executions, cannot give every new prompt one answer per enabled AI model, so the rest run when the allowance resets at this time (00:00 Europe/Madrid). It counts this request&#39;s prompts against what was left when it arrived, not first runs other requests queued moments earlier. Null otherwise, when the allowance is unlimited, when tracked is false or when the account is not active | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


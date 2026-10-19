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
**RequestId** | **string** |  | 
**LengthWarning** | **string** | Which tracked AI models will skip new prompts that are too long for them | 
**PromptsAvailable** | **int** | Prompt slots left on the plan; null when unlimited | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


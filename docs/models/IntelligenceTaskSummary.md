# LLMPulse.SDK.Model.IntelligenceTaskSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PublicId** | **string** |  | 
**TaskType** | **string** |  | 
**Title** | **string** |  | 
**Status** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**ResultVersion** | **string** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \&quot;0\&quot; until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text | 
**PromptId** | **int** |  | 
**PromptText** | **string** |  | 
**WordCount** | **int** |  | 
**ManuallyEditedAt** | **DateTime** | When the content was last edited by hand; null while the output is as generated | 
**ProcessedAt** | **DateTime** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


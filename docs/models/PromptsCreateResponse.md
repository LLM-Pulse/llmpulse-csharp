# LLMPulse.SDK.Model.PromptsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Created** | **int** |  | [optional] 
**Skipped** | **int** |  | [optional] 
**TotalAfter** | **int** |  | [optional] 
**PromptsAvailable** | **int** |  | [optional] 
**Tracked** | **bool** | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes | [optional] 
**UntrackedReason** | **string** | Why tracked is false: paused or project_limit. Null when tracked | [optional] 
**Warning** | **string** | What to do when tracked is false. Null when tracked | [optional] 
**Data** | [**List&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


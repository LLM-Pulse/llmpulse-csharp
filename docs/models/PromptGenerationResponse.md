# LLMPulse.SDK.Model.PromptGenerationResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **Guid** | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) | 
**ProjectId** | **int** |  | 
**Source** | **string** |  | 
**Status** | **string** |  | 
**Params** | [**PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  | 
**CreatedAt** | **DateTime** |  | 
**SuggestionsCount** | **int** |  | 
**Suggestions** | [**List&lt;SuggestedPrompt&gt;**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status | 
**RequestId** | **string** |  | 
**FinishedAt** | **DateTime** |  | 
**Error** | [**PromptGenerationResponseError**](PromptGenerationResponseError.md) |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


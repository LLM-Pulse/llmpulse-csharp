# LLMPulse.SDK.Model.ProjectDraftSuggestions
AI suggestions for a step. Only the key of the suggested step is sent, and only when status is ready

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** | ready, none (not requested, or nothing cached yet) or failed | 
**Step** | **string** | The step the suggestions are for (details, prompts or competitors) | [optional] 
**Details** | [**ProjectDraftSuggestionsDetails**](ProjectDraftSuggestionsDetails.md) |  | [optional] 
**Prompts** | **List&lt;string&gt;** |  | [optional] 
**Competitors** | [**List&lt;ProjectDraftSuggestionsCompetitorsInner&gt;**](ProjectDraftSuggestionsCompetitorsInner.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


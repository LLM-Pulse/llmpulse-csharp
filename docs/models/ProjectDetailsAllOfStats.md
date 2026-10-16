# LLMPulse.SDK.Model.ProjectDetailsAllOfStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PromptsCount** | **int** | Active prompts in the project | [optional] 
**PromptsAvailable** | **int** | Prompts that can still be added to this project, the lower of its free slots under prompt_limit and the prompts left in the account quota; null when neither caps it | [optional] 
**PromptsByBrandKind** | [**ProjectDetailsAllOfStatsPromptsByBrandKind**](ProjectDetailsAllOfStatsPromptsByBrandKind.md) |  | [optional] 
**CompetitorsCount** | **int** |  | [optional] 
**CollectionsCount** | **int** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


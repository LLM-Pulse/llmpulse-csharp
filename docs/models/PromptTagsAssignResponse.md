# LLMPulse.SDK.Model.PromptTagsAssignResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**PromptsTargeted** | **int** | Prompts of the project among prompt_ids | 
**TagsAttached** | [**List&lt;TagRef&gt;**](TagRef.md) |  | 
**NewLinksCreated** | **int** |  | 
**SkippedAlreadyLinked** | **int** |  | 
**MissingTagNames** | **List&lt;string&gt;** | tag_names that matched no tag and were not created | 
**IgnoredPromptIds** | **List&lt;int&gt;** | prompt_ids that are not prompts of this project | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


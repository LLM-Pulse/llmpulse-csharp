# LLMPulse.SDK.Model.PromptTagsRemoveResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**PromptsTargeted** | **int** | Prompts of the project among prompt_ids | 
**TagsDetached** | [**List&lt;TagRef&gt;**](TagRef.md) |  | 
**LinksRemoved** | **int** |  | 
**SkippedNotLinked** | **int** |  | 
**MissingTagNames** | **List&lt;string&gt;** | tag_names that matched no tag | 
**IgnoredPromptIds** | **List&lt;int&gt;** | prompt_ids that are not prompts of this project | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


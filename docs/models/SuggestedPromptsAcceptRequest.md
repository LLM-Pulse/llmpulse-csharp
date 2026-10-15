# LLMPulse.SDK.Model.SuggestedPromptsAcceptRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Ids** | **List&lt;int&gt;** | Suggestion ids to accept (max 100) | 
**TagIds** | **List&lt;int&gt;** | One tag id to put the new prompts in | [optional] 
**TagNames** | **List&lt;string&gt;** | One tag name (case-insensitive) to put the new prompts in | [optional] 
**CreateMissing** | **bool** | Create the tag named in tag_names when it does not exist | [optional] [default to false]

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


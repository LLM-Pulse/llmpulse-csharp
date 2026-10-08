# LLMPulse.SDK.Model.PromptExecutionRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PromptId** | **int** |  | 
**Model** | **string** |  | 
**HasMention** | **bool** |  | 
**HasCitation** | **bool** |  | 
**MentionsCount** | **int** | 1 when the answer mentions the brand, otherwise 0 | 
**CitationsCount** | **int** | 1 when the answer cites the brand, otherwise 0 | 
**AppUrl** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | 
**ExecutedAt** | **DateTime** | Null while the answer is still pending | 
**DurationMs** | **decimal** |  | 
**Success** | **bool** | Null while the answer is still pending | 
**FanOutQueries** | **List&lt;string&gt;** | Sub-queries the model issued while answering; null when the model reports none | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


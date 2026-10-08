# LLMPulse.SDK.Model.CitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Name** | **string** | The project&#39;s brand name (its name when no brand name is set) | 
**PromptId** | **int** |  | 
**PromptExecutionId** | **int** |  | 
**Url** | **string** | Normalized cited URL (tracking parameters and fragment removed) | 
**CreatedAt** | **DateTime** |  | 
**Domain** | **string** | Host of the cited URL without www.; null when the URL has no parsable host | 
**Position** | **int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.AllCitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** | The citation&#39;s id, unique within its actor_type | 
**ActorType** | **string** | project (your brand) or competitor | 
**PromptId** | **int** |  | 
**PromptExecutionId** | **int** |  | 
**Url** | **string** | Normalized cited URL (tracking parameters and fragment removed) | 
**CreatedAt** | **DateTime** |  | 
**CompetitorId** | **int** | Competitor rows only | [optional] 
**Name** | **string** | The project&#39;s brand name (its name when no brand name is set), or the competitor&#39;s brand name | 
**Domain** | **string** | On project rows the host of the cited URL without www. (null when it has no parsable host); on competitor rows the competitor&#39;s bare domain | 
**Position** | **int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.CompetitorSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | The suggestion key (brands) or the id of one citing source row (citations) | 
**Domain** | **string** |  | 
**MatchingNames** | **List&lt;string&gt;** | The names a tracked competitor would be matched by; empty for a cited domain | 
**BrandName** | **string** | The proposed brand name; null for a cited domain | [optional] 
**Mentions** | **int** | Answers naming the brand, when the discovery counted them (brands only) | [optional] 
**Citations** | **int** | Answers citing the domain (citations only) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


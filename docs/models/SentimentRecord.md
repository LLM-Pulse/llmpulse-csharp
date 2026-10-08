# LLMPulse.SDK.Model.SentimentRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PromptExecutionId** | **int** |  | 
**PromptText** | **string** |  | 
**Model** | **string** |  | 
**Analysis** | **string** |  | 
**IsBrandSentiment** | **bool** |  | 
**CreatedAt** | **DateTime** |  | 
**Score** | **decimal** | From -1 (very negative) to 1 (very positive) | 
**Comment** | **string** |  | 
**Topics** | **string** | Comma-separated topics | 
**CompetitorId** | **int** | Null for a sentiment about the project&#39;s own brand | 
**CompetitorName** | **string** | Null for a sentiment about the project&#39;s own brand | 
**ExecutedAt** | **DateTime** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


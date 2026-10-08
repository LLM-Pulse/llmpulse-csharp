# LLMPulse.SDK.Model.RecommendationSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**ProjectId** | **int** |  | 
**RecommendationType** | **string** |  | 
**Status** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**TotalRecommendations** | **int** |  | 
**HighPriorityCount** | **int** |  | 
**Summary** | [**RecommendationSummarySummary**](RecommendationSummarySummary.md) |  | 
**Context** | **Object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract | 
**ErrorMessage** | **string** | Set only when status is failed | 
**GeneratedAt** | **DateTime** | Null until the generation completes | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.RecommendationDetailResponse
One recommendation run with its items

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
**Summary** | [**RecommendationDetailResponseSummary**](RecommendationDetailResponseSummary.md) |  | 
**Context** | **Object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract | 
**ReportData** | **Dictionary&lt;string, Object&gt;** | The stored run, including the evidence indices (prompts_index, citations_index, own_content_index and others) that the source_refs codes of the items point to. Its keys are not a stable contract | 
**ItemCounts** | [**RecommendationDetailResponseItemCounts**](RecommendationDetailResponseItemCounts.md) |  | 
**Items** | [**List&lt;RecommendationItem&gt;**](RecommendationItem.md) |  | 
**RequestId** | **string** |  | 
**ErrorMessage** | **string** | Set only when status is failed | 
**GeneratedAt** | **DateTime** | Null until the generation completes | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


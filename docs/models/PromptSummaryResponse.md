# LLMPulse.SDK.Model.PromptSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlanRequiredFields** | **List&lt;string&gt;** | The row fields left out because they need a higher plan (the sentiment fields below Growth); empty when none is | 
**ProjectId** | **int** |  | [optional] 
**From** | **DateTime** |  | [optional] 
**To** | **DateTime** |  | [optional] 
**Filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  | [optional] 
**Breakdown** | **string** |  | [optional] 
**Sort** | **string** |  | [optional] 
**SortDir** | **string** |  | [optional] 
**Page** | **int** |  | [optional] 
**PerPage** | **int** |  | [optional] 
**Total** | **int** |  | [optional] 
**Data** | [**List&lt;PromptSummaryRow&gt;**](PromptSummaryRow.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


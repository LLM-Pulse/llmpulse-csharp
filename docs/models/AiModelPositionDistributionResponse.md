# LLMPulse.SDK.Model.AiModelPositionDistributionResponse
The positions at which one or two brands were mentioned, in four buckets, per period of the window.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**From** | **DateTime** |  | 
**To** | **DateTime** |  | 
**Filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  | 
**Granularity** | **string** |  | 
**Brands** | [**List&lt;AiModelPositionDistributionBrand&gt;**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window | 
**MaxStackedValue** | **int** | The largest mentions count of one period across the brands, for a shared chart axis | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


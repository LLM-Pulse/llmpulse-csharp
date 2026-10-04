# LLMPulse.SDK.Model.AiOrdersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Platform** | **string** |  | 
**From** | **DateOnly** |  | 
**To** | **DateOnly** |  | 
**Totals** | [**AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  | 
**BySource** | [**List&lt;AiOrdersResponseBySourceInner&gt;**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first | 
**Series** | [**List&lt;AiOrdersResponseSeriesInner&gt;**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first | 
**RequestId** | **string** |  | 
**Currency** | **string** | ISO 4217 code of the most recent stored day; null when the window holds no stored order | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


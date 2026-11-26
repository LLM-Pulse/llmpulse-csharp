# LLMPulse.SDK.Model.CitationSeries
The answers citing it under the same filters, by AI model and per period of the account tracking cadence

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Granularity** | **string** |  | 
**Total** | **int** | Equal to total_responses | 
**ByModel** | **Dictionary&lt;string, int&gt;** | Answers per AI model, keyed by model, largest first | 
**Data** | [**List&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


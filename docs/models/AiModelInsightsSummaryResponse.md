# LLMPulse.SDK.Model.AiModelInsightsSummaryResponse
One entry per AI model the account has enabled or that answered in the window, in the in-app column order: the models list, which every per-model list and map in summary follows. A share, net sentiment or market share value with nothing behind it is null, because 0 is a real value; counts, totals and weighted visibility scores stay 0.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlanRequiredFields** | **List&lt;string&gt;** | The summary sections left out because they need a higher plan (brand_net_sentiment_by_model and sentiment_market_share below Growth); empty when none is | 
**ProjectId** | **int** |  | [optional] 
**From** | **DateTime** |  | [optional] 
**To** | **DateTime** |  | [optional] 
**Filters** | [**AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md) |  | [optional] 
**Models** | [**List&lt;AiModelInsightsModel&gt;**](AiModelInsightsModel.md) | The AI models the account has enabled or that answered in the window, in the in-app column order | [optional] 
**Summary** | [**AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


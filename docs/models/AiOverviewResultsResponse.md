# LLMPulse.SDK.Model.AiOverviewResultsResponse
How often Google AI Overviews returned a result for the project's prompts. A result rate is a percentage (0-100) of the AI Overview runs, 0 when there is none.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**From** | **DateTime** |  | 
**To** | **DateTime** |  | 
**Filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  | 
**Granularity** | **string** |  | 
**Summary** | [**AiOverviewResultCounts**](AiOverviewResultCounts.md) |  | 
**Chart** | [**List&lt;AiOverviewResultsResponseChartInner&gt;**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included | 
**ByPrompt** | [**AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


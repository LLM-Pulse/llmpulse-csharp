# LLMPulse.SDK.Model.AiTrafficResponse
Visits from AI assistants measured by the connected web analytics provider, by day over the window.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Provider** | **string** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano | 
**From** | **DateOnly** |  | 
**To** | **DateOnly** |  | 
**Granularity** | **string** |  | 
**Totals** | [**AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  | 
**BySource** | [**List&lt;AiTrafficResponseBySourceInner&gt;**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first | 
**Timeseries** | **Dictionary&lt;string, Dictionary&lt;string, int&gt;&gt;** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


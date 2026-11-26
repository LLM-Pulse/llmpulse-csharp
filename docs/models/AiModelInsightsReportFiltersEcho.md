# LLMPulse.SDK.Model.AiModelInsightsReportFiltersEcho
The filters a position distribution or AI Overview report was computed with, as the server resolved them. A filter that was not given is left out, except from, to, granularity and competitors.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**From** | **DateTime** |  | 
**To** | **DateTime** |  | 
**Granularity** | **string** |  | 
**Competitors** | **List&lt;int&gt;** | Competitor ids from the competitors parameter; empty when it was not given | 
**CountryCode** | **string** | Comma-separated country codes | [optional] 
**LanguageCode** | **string** | Comma-separated language codes | [optional] 
**CollectionId** | **string** | Comma-separated collection ids | [optional] 
**PromptType** | **string** | Comma-separated prompt types | [optional] 
**BrandKind** | **string** |  | [optional] 
**Model** | **string** | The model filter; always ai_overview on the AI Overview report | [optional] 
**Brand1** | **string** | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand | [optional] 
**Brand2** | **string** | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.AiModelInsightsFiltersEcho
The filters the summary was computed with, as the server resolved them. A filter that was not given is left out, except granularity and competitors.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**From** | **DateTime** |  | [optional] 
**To** | **DateTime** |  | [optional] 
**Granularity** | **string** | day, week or month; day when not given | [optional] 
**CountryCode** | **string** | Comma-separated country codes | [optional] 
**LanguageCode** | **string** | Comma-separated language codes | [optional] 
**CollectionId** | **string** | Comma-separated collection ids | [optional] 
**PromptType** | **string** | Comma-separated prompt types | [optional] 
**BrandKind** | **string** |  | [optional] 
**Competitors** | **List&lt;int&gt;** | Competitor ids from the competitors parameter; empty when it was not given | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


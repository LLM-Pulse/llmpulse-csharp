# LLMPulse.SDK.Model.MetricsFiltersEcho
The filters the response was computed with, as the server resolved them. Each endpoint echoes only the keys it reads; a filter that was not given comes back null (or an empty list).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Metrics** | **List&lt;string&gt;** | Requested metrics after alias resolution (mention_rate is echoed as visibility) | [optional] 
**Granularity** | **string** | day, week or month | [optional] 
**Model** | **string** | The model filter, or null when absent or not enabled for the account | [optional] 
**CollectionId** | **string** | The collection_id parameter as sent (one id or a comma-separated list) | [optional] 
**CollectionIds** | **List&lt;int&gt;** |  | [optional] 
**Domains** | **List&lt;string&gt;** |  | [optional] 
**CountryCode** | **string** | Comma-separated country codes | [optional] 
**LanguageCode** | **string** | Comma-separated language codes | [optional] 
**Prompt** | **int** | The prompt id filter | [optional] 
**PromptType** | **string** | Comma-separated prompt types | [optional] 
**BrandKind** | **string** |  | [optional] 
**Competitors** | **List&lt;int&gt;** | Competitor ids from the competitors parameter; empty when it was not given | [optional] 
**IncludeProject** | **bool** |  | [optional] 
**Query** | **string** | Only present when a query filter was given | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


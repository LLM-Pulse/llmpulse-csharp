# LLMPulse.SDK.Api.AIModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAiModelInsightsSummary**](AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary |
| [**GetAiModelPositionDistribution**](AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison |
| [**GetAiOverviewResults**](AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability |
| [**GetDeclinedAnswers**](AIModelInsightsApi.md#getdeclinedanswers) | **GET** /reports/ai_model_insights/declined_answers | Declined answers (decline rate) |

<a id="getaimodelinsightssummary"></a>
# **GetAiModelInsightsSummary**
> AiModelInsightsSummaryResponse GetAiModelInsightsSummary (int projectId, int range = null, DateTime from = null, DateTime to = null, string granularity = null, string collectionId = null, string countryCode = null, string languageCode = null, string promptType = null, string brandKind = null, string competitors = null)

AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape `{ type, id, competitor_id, name, domain }` with bare (scheme-less) domains. Rows cover the AI models the account has enabled or that answered in the window. A share, net sentiment or market share value with nothing behind it is null; counts, totals and weighted visibility scores stay 0.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **competitors** | **string** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional]  |

### Return type

[**AiModelInsightsSummaryResponse**](AiModelInsightsSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaimodelpositiondistribution"></a>
# **GetAiModelPositionDistribution**
> void GetAiModelPositionDistribution (int projectId, int range = null, DateTime from = null, DateTime to = null, string granularity = null, string collectionId = null, string countryCode = null, string languageCode = null, string promptType = null, string brandKind = null, string model = null, int brand1 = null, int brand2 = null)

Position distribution comparison


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **model** | **string** | Restrict the comparison to one AI model of AI Model Insights, whether or not that model is enabled for the API key&#39;s user. Any other value returns 422 ERR_INVALID_PARAM (invalid model). | [optional]  |
| **brand1** | **int** | Competitor ID for the first comparison brand (omit to compare project brand) | [optional]  |
| **brand2** | **int** |  | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bucketed position totals + chart-ready series |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaioverviewresults"></a>
# **GetAiOverviewResults**
> void GetAiOverviewResults (int projectId, int range = null, DateTime from = null, DateTime to = null, string granularity = null, string collectionId = null, string countryCode = null, string languageCode = null, string promptType = null, string brandKind = null, int page = null, int perPage = null)

Google AI Overview result availability


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI Overview result-availability data + per-prompt table |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getdeclinedanswers"></a>
# **GetDeclinedAnswers**
> AiModelDeclinedAnswersResponse GetDeclinedAnswers (int projectId, int range = null, DateTime from = null, DateTime to = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string promptType = null, string brandKind = null, int page = null, int perPage = null)

Declined answers (decline rate)

The Declined answers tab of AI Model Insights. A model declines a prompt for its own safety filters (safety_filter) or because it refuses the topic itself, such as tobacco, gambling or alcohol (topic_refusal); today only Gemini declines. A declined answer counts as no answer and never lowers visibility. The chart has one point per tracking period at the account's cadence that holds an answer of the model, and the window starts at the tracking period holding its first day.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **model** | **string** | The model whose declines to read, whether or not it is enabled for the API key&#39;s user. Default: gemini. Any other model returns 422 ERR_INVALID_PARAM (invalid model). | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**AiModelDeclinedAnswersResponse**](AiModelDeclinedAnswersResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Decline counts and rates for the window, per tracking period and per prompt |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


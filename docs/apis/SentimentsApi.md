# LLMPulse.SDK.Api.SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetSentimentTags**](SentimentsApi.md#getsentimenttags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**GetSentimentTopics**](SentimentsApi.md#getsentimenttopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**ListSentimentCategories**](SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**ListSentimentRecords**](SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records (Growth plan or above) |

<a id="getsentimenttags"></a>
# **GetSentimentTags**
> SentimentTagsResponse GetSentimentTags (int projectId, int range = null, DateTime from = null, DateTime to = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, string analysis = null, string topic = null, string query = null, string brand = null, string sort = null, string sortDir = null, int page = null, int perPage = null, string output = null)

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **analysis** | **string** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional]  |
| **topic** | **string** | Only sentiments tagged with this topic (case-insensitive) | [optional]  |
| **query** | **string** | Only sentiments whose answer or prompt text contains this text | [optional]  |
| **brand** | **string** | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional]  |
| **sort** | **string** | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] |
| **sortDir** | **string** |  | [optional] [default to desc] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**SentimentTagsResponse**](SentimentTagsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tag rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsentimenttopics"></a>
# **GetSentimentTopics**
> SentimentTopicsResponse GetSentimentTopics (int projectId, int range = null, DateTime from = null, DateTime to = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, string analysis = null, string topic = null, string query = null, string brand = null, string sort = null, string sortDir = null, int page = null, int perPage = null, string output = null)

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, `brand` empty counts your own brand, `all` every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **analysis** | **string** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional]  |
| **topic** | **string** | Only sentiments tagged with this topic (case-insensitive) | [optional]  |
| **query** | **string** | Only sentiments whose answer or prompt text contains this text | [optional]  |
| **brand** | **string** | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional]  |
| **sort** | **string** | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] |
| **sortDir** | **string** |  | [optional] [default to desc] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**SentimentTopicsResponse**](SentimentTopicsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated topic rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsentimentcategories"></a>
# **ListSentimentCategories**
> void ListSentimentCategories (int projectId, string output = null)

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sentiment buckets |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsentimentrecords"></a>
# **ListSentimentRecords**
> SentimentsResponse ListSentimentRecords (int projectId, int competitorId = null, bool brandOnly = null, string analysis = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, DateTime from = null, DateTime to = null, int page = null, int perPage = null)

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitorId** | **int** |  | [optional]  |
| **brandOnly** | **bool** |  | [optional]  |
| **analysis** | **string** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional]  |
| **model** | **string** | Filter by one AI model. Here an unknown value, or a model the API key&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**SentimentsResponse**](SentimentsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sentiments |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


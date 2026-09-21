# LLMPulse.SDK.Api.SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListSentimentCategories**](SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories |
| [**ListSentimentRecords**](SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records |

<a id="listsentimentcategories"></a>
# **ListSentimentCategories**
> void ListSentimentCategories (int projectId, string output = null)

List sentiment categories

Sentiment metric keys + labels + colors. For records, use /sentiments.


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
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sentiment buckets |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsentimentrecords"></a>
# **ListSentimentRecords**
> void ListSentimentRecords (int projectId, int competitorId = null, bool brandOnly = null, string analysis = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, DateTime from = null, DateTime to = null, int page = null, int perPage = null)

List sentiment records


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitorId** | **int** |  | [optional]  |
| **brandOnly** | **bool** |  | [optional]  |
| **analysis** | **string** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional]  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

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
| **200** | Paginated sentiments |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


# LLMPulse.SDK.Api.SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListSentimentRecords**](SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records |

<a id="listsentimentrecords"></a>
# **ListSentimentRecords**
> void ListSentimentRecords (int projectId, int competitorId = null, bool brandOnly = null, string analysis = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, DateTime from = null, DateTime to = null, int page = null, int perPage = null)

List sentiment records


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitorId** | **int** |  | [optional]  |
| **brandOnly** | **bool** |  | [optional]  |
| **analysis** | **string** |  | [optional]  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
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


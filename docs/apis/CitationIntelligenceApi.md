# LLMPulse.SDK.Api.CitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetCitedUrlContent**](CitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**GetCitedUrlDetail**](CitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**GetMentionsByCitingDomain**](CitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**ListCitationGroups**](CitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**ListCitedUrlOccurrences**](CitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |

<a id="getcitedurlcontent"></a>
# **GetCitedUrlContent**
> void GetCitedUrlContent (int projectId, string urlSha256)

Cited URL cached content


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **urlSha256** | **string** | 64-character hex SHA-256 of the cited URL |  |

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
| **200** | Sanitized cached content + mention evidence |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getcitedurldetail"></a>
# **GetCitedUrlDetail**
> void GetCitedUrlDetail (int projectId, string urlSha256)

Cited URL detail


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **urlSha256** | **string** | 64-character hex SHA-256 of the cited URL |  |

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
| **200** | URL-level intelligence |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getmentionsbycitingdomain"></a>
# **GetMentionsByCitingDomain**
> void GetMentionsByCitingDomain (int projectId, List<string> domains, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **domains** | [**List&lt;string&gt;**](string.md) | Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com |  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |

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
| **200** | Mention share per citing domain |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcitationgroups"></a>
# **ListCitationGroups**
> void ListCitationGroups (int projectId, string view = null, int page = null, int perPage = null, string order = null, string direction = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null, string query = null, string sourceType = null, string sentiment = null, string contentGap = null)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **view** | **string** |  | [optional] [default to url] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **order** | **string** |  | [optional]  |
| **direction** | **string** |  | [optional]  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **query** | **string** |  | [optional]  |
| **sourceType** | **string** |  | [optional]  |
| **sentiment** | **string** |  | [optional]  |
| **contentGap** | **string** |  | [optional]  |

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
| **200** | Grouped citation intelligence |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcitedurloccurrences"></a>
# **ListCitedUrlOccurrences**
> void ListCitedUrlOccurrences (int projectId, string urlSha256, int page = null, int perPage = null)

Cited URL occurrences


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **urlSha256** | **string** | 64-character hex SHA-256 of the cited URL |  |
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
| **200** | Paginated occurrences |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


# LLMPulse.SDK.Api.GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateIntelligenceTask**](GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**GetIntelligenceTask**](GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**ListIntelligenceTasks**](GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks |

<a id="createintelligencetask"></a>
# **CreateIntelligenceTask**
> IntelligenceTask CreateIntelligenceTask (IntelligenceTaskCreateRequest intelligenceTaskCreateRequest)

Create a GEO Writer task


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **intelligenceTaskCreateRequest** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md) |  |  |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getintelligencetask"></a>
# **GetIntelligenceTask**
> IntelligenceTask GetIntelligenceTask (int projectId, string id)

Get a GEO Writer task


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **string** | Numeric task ID or public_id string token |  |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Task with result_data when completed |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listintelligencetasks"></a>
# **ListIntelligenceTasks**
> void ListIntelligenceTasks (int projectId, string taskType = null, string status = null, int page = null, int perPage = null)

List GEO Writer tasks


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **taskType** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |
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
| **200** | Paginated tasks |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


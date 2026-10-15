# LLMPulse.SDK.Api.RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetRecommendation**](RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**LaunchRecommendations**](RecommendationsApi.md#launchrecommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**ListRecommendations**](RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs |
| [**UpdateRecommendationItem**](RecommendationsApi.md#updaterecommendationitem) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |

<a id="getrecommendation"></a>
# **GetRecommendation**
> void GetRecommendation (int projectId, int id, string itemStatus = null, bool resolveSourceRefs = null)

Get recommendation run with items


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **int** |  |  |
| **itemStatus** | **string** |  | [optional]  |
| **resolveSourceRefs** | **bool** |  | [optional] [default to true] |

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
| **200** | Recommendation detail with items |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="launchrecommendations"></a>
# **LaunchRecommendations**
> void LaunchRecommendations (LaunchRecommendationsRequest launchRecommendationsRequest)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **launchRecommendationsRequest** | [**LaunchRecommendationsRequest**](LaunchRecommendationsRequest.md) |  |  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Generation launched (status pending) |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listrecommendations"></a>
# **ListRecommendations**
> RecommendationsResponse ListRecommendations (int projectId, string recommendationType = null, string status = null, int page = null, int perPage = null)

List recommendation runs


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **recommendationType** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**RecommendationsResponse**](RecommendationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated recommendations |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updaterecommendationitem"></a>
# **UpdateRecommendationItem**
> RecommendationItemUpdateResponse UpdateRecommendationItem (int id, int itemId, UpdateRecommendationItemRequest updateRecommendationItemRequest)

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between `active`, `completed` and `archived`, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps `status_changed_at`. Returns the item in the shape `GET /recommendations/{id}` lists items. Requires a `read_write` scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** | Recommendation run id |  |
| **itemId** | **int** | Item id, from the items of GET /recommendations/{id} |  |
| **updateRecommendationItemRequest** | [**UpdateRecommendationItemRequest**](UpdateRecommendationItemRequest.md) |  |  |

### Return type

[**RecommendationItemUpdateResponse**](RecommendationItemUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated item |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


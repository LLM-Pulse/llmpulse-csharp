# LLMPulse.SDK.Api.AnnotationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateAnnotation**](AnnotationsApi.md#createannotation) | **POST** /annotations | Create a timeline annotation |
| [**DeleteAnnotation**](AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation |
| [**ListAnnotations**](AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations |
| [**UpdateAnnotation**](AnnotationsApi.md#updateannotation) | **PATCH** /annotations/{id} | Update a timeline annotation |

<a id="createannotation"></a>
# **CreateAnnotation**
> void CreateAnnotation (CreateAnnotationRequest createAnnotationRequest)

Create a timeline annotation

Marks a date in the project timeseries with a title + description. Available on every plan. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createAnnotationRequest** | [**CreateAnnotationRequest**](CreateAnnotationRequest.md) |  |  |

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
| **201** | Created |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deleteannotation"></a>
# **DeleteAnnotation**
> void DeleteAnnotation (int projectId, int id)

Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Available on every plan and requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **int** |  |  |

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
| **200** | Deleted |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listannotations"></a>
# **ListAnnotations**
> void ListAnnotations (int projectId, DateOnly from = null, DateOnly to = null, int annotationCategoryId = null, int page = null, int perPage = null)

List timeline annotations

Lists project timeline annotations, newest first. Rows can come from manual notes, project automations, GEO tests, or platform events. The origin field distinguishes them; editable says whether the requesting user may modify the row. Available on every plan.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **from** | **DateOnly** |  | [optional]  |
| **to** | **DateOnly** |  | [optional]  |
| **annotationCategoryId** | **int** |  | [optional]  |
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
| **200** | Paginated annotations |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateannotation"></a>
# **UpdateAnnotation**
> void UpdateAnnotation (int id, UpdateAnnotationRequest updateAnnotationRequest)

Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Available on every plan and requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** |  |  |
| **updateAnnotationRequest** | [**UpdateAnnotationRequest**](UpdateAnnotationRequest.md) |  |  |

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
| **200** | Updated |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


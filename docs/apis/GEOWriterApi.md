# LLMPulse.SDK.Api.GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateIntelligenceTask**](GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**GetIntelligenceTask**](GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**ListIntelligenceTasks**](GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**RevertIntelligenceTaskContent**](GEOWriterApi.md#revertintelligencetaskcontent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**UpdateIntelligenceTaskContent**](GEOWriterApi.md#updateintelligencetaskcontent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |

<a id="createintelligencetask"></a>
# **CreateIntelligenceTask**
> IntelligenceTask CreateIntelligenceTask (IntelligenceTaskCreateRequest intelligenceTaskCreateRequest)

Create a GEO Writer task

Creates a GEO Writer task, processed asynchronously: poll GET /intelligence_tasks/{id} until status is completed. Prompt-based mode takes prompt_id; agentic mode takes custom_topic and/or user_instructions. task_type product_listing is API-only and serves store apps: send a product object (title required) and optionally prompt_ids, and the completed result_data holds ready-to-apply product page copy. Edit and revert it with PATCH /intelligence_tasks/{id} and POST /intelligence_tasks/{id}/revert. Requires a `read_write` scope API key.


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
| **403** | API key lacks write permission |  -  |
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
> IntelligenceTasksResponse ListIntelligenceTasks (int projectId, string taskType = null, string status = null, int page = null, int perPage = null)

List GEO Writer tasks


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **taskType** | **string** |  | [optional]  |
| **status** | **string** | Keep only the tasks in this status. Discarded tasks are never listed, so discarded returns an empty page. | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**IntelligenceTasksResponse**](IntelligenceTasksResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tasks |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="revertintelligencetaskcontent"></a>
# **RevertIntelligenceTaskContent**
> IntelligenceTask RevertIntelligenceTaskContent (int projectId, string id)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output as it was generated. On a product_listing task, description_html comes back with only p, ul, ol, li, strong, em, h3 and br and no attributes, cleaned like an edit. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.


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
| **200** | Task restored to its generated output |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateintelligencetaskcontent"></a>
# **UpdateIntelligenceTaskContent**
> IntelligenceTaskUpdateResponse UpdateIntelligenceTaskContent (string id, IntelligenceTaskUpdateRequest intelligenceTaskUpdateRequest)

Edit GEO Writer task content

Edits the text of a completed task in place. `edits` maps dotted paths into result_data (for example `title` or `sections.0.content`) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank `title`, a value over 20,000 characters or an empty `edits` object is rejected with ERR_INVALID_PARAM and nothing is written. Send the `result_version` you last read with the edits: when the task was regenerated since, the request is refused with ERR_STALE_CONTENT (409), nothing is written and `error.meta.result_version` holds the current token. Without `result_version` the edits apply to whatever the task holds now. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer. On a product_listing task, description_html keeps only p, ul, ol, li, strong, em, h3 and br, with no attributes: other markup is stripped, not refused, so read the stored value from the response. A revert restores the generated description cleaned the same way.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Numeric task ID or public_id string token |  |
| **intelligenceTaskUpdateRequest** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md) |  |  |

### Return type

[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated task with the paths that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **409** | The task was regenerated since the result_version in the request was read (ERR_STALE_CONTENT). Nothing was written; error.meta.result_version holds the current token. Read the task again and resend the edits |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


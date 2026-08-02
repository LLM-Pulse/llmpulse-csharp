# LLMPulse.SDK.Api.PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AssignPromptTags**](PromptsApi.md#assignprompttags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**CreatePrompts**](PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts |
| [**DeletePrompt**](PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt |

<a id="assignprompttags"></a>
# **AssignPromptTags**
> void AssignPromptTags (AssignPromptTagsRequest assignPromptTagsRequest)

Bulk-attach tags to prompts

Idempotent bulk assignment of tags (Collections) to existing prompts. Tags can be resolved by id or by name (case-insensitive). Use `create_missing: true` to auto-create unknown tag names. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **assignPromptTagsRequest** | [**AssignPromptTagsRequest**](AssignPromptTagsRequest.md) |  |  |

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
| **200** | Tags attached |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createprompts"></a>
# **CreatePrompts**
> PromptsCreateResponse CreatePrompts (PromptsCreateRequest promptsCreateRequest)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **promptsCreateRequest** | [**PromptsCreateRequest**](PromptsCreateRequest.md) |  |  |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

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

<a id="deleteprompt"></a>
# **DeletePrompt**
> void DeletePrompt (int projectId, int id)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a `read_write` scope API key.


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
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


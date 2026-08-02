# LLMPulse.SDK.Api.ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateProject**](ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode) |
| [**CreateProjectDraft**](ProjectsApi.md#createprojectdraft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**FinalizeProjectDraft**](ProjectsApi.md#finalizeprojectdraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**GetProjectDraft**](ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**UpdateProjectDraft**](ProjectsApi.md#updateprojectdraft) | **PATCH** /project_drafts/{id} | Submit a wizard step |

<a id="createproject"></a>
# **CreateProject**
> ProjectCreateResponse CreateProject (ProjectCreateRequest projectCreateRequest)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectCreateRequest** | [**ProjectCreateRequest**](ProjectCreateRequest.md) |  |  |

### Return type

[**ProjectCreateResponse**](ProjectCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **200** | Idempotent replay (existing external_identifier) |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="createprojectdraft"></a>
# **CreateProjectDraft**
> void CreateProjectDraft (CreateProjectDraftRequest createProjectDraftRequest)

Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest=false to skip AI and respond instantly. Drafts expire after 24h. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createProjectDraftRequest** | [**CreateProjectDraftRequest**](CreateProjectDraftRequest.md) |  |  |

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
| **201** | Draft created; envelope with draft state, suggestions and limits |  -  |
| **422** | Invalid parameters |  -  |
| **403** | API key lacks write permission |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="finalizeprojectdraft"></a>
# **FinalizeProjectDraft**
> void FinalizeProjectDraft (string id, FinalizeProjectDraftRequest finalizeProjectDraftRequest = null)

Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **finalizeProjectDraftRequest** | [**FinalizeProjectDraftRequest**](FinalizeProjectDraftRequest.md) |  | [optional]  |

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
| **201** | Project created |  -  |
| **200** | Idempotent replay |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getprojectdraft"></a>
# **GetProjectDraft**
> void GetProjectDraft (string id, bool includeSuggestions = null)

Read a project draft


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Draft id (draft_...) |  |
| **includeSuggestions** | **bool** | Cache-only: returns suggestions for the current step if already generated, never triggers AI | [optional] [default to false] |

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
| **200** | Draft envelope |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateprojectdraft"></a>
# **UpdateProjectDraft**
> void UpdateProjectDraft (string id, UpdateProjectDraftRequest updateProjectDraftRequest)

Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (`ERR_DRAFT_STATE` otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** |  |  |
| **updateProjectDraftRequest** | [**UpdateProjectDraftRequest**](UpdateProjectDraftRequest.md) |  |  |

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
| **200** | Draft envelope with next-step suggestions |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


# LLMPulse.SDK.Api.ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateProject**](ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode) |
| [**CreateProjectDraft**](ProjectsApi.md#createprojectdraft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**FinalizeProjectDraft**](ProjectsApi.md#finalizeprojectdraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**GetProjectDetails**](ProjectsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details |
| [**GetProjectDraft**](ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**ListLocales**](ProjectsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data |
| [**ListModels**](ProjectsApi.md#listmodels) | **GET** /dimensions/models | List models with data |
| [**ListProjects**](ProjectsApi.md#listprojects) | **GET** /dimensions/projects | List projects |
| [**UpdateProject**](ProjectsApi.md#updateproject) | **PATCH** /projects/{id} | Update a project profile (Brand Book) |
| [**UpdateProjectDraft**](ProjectsApi.md#updateprojectdraft) | **PATCH** /project_drafts/{id} | Submit a wizard step |

<a id="createproject"></a>
# **CreateProject**
> ProjectCreateResponse CreateProject (ProjectCreateRequest projectCreateRequest)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), collections tagging those prompts, competitors, weekly email subscription. The response lists same_domain_projects so an accidental duplicate is visible; it never blocks the create. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.


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
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
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
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |

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
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getprojectdetails"></a>
# **GetProjectDetails**
> ProjectDetails GetProjectDetails (int id)

Project details

Detailed info for one project: matching_names, additional_owned_domains, industry, business model, primary products, target audience, brand voice, locale, app store IDs, prompt_limit (the project's own prompt cap, null without one), stats (incl. prompts_by_brand_kind counts and prompts_available, how many prompts can still be added: the lower of the project's free slots and the account's remaining prompts, null when neither caps it) and data_coverage (models, countries and languages with data).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** |  |  |

### Return type

[**ProjectDetails**](ProjectDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Project details |  -  |
| **404** | Resource not found |  -  |

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
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listlocales"></a>
# **ListLocales**
> LocalesResponse ListLocales (int projectId)

List locales with data


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |

### Return type

[**LocalesResponse**](LocalesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Locales |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmodels"></a>
# **ListModels**
> ModelsResponse ListModels (int projectId)

List models with data


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |

### Return type

[**ModelsResponse**](ModelsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Models |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listprojects"></a>
# **ListProjects**
> ListProjects200Response ListProjects (string output = null)

List projects

All projects accessible with your API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Projects |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateproject"></a>
# **UpdateProject**
> ProjectUpdateResponse UpdateProject (int id, UpdateProjectRequest updateProjectRequest)

Update a project profile (Brand Book)

Updates the project name and profile, the same fields as Project Settings: name, brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names, and the additional owned domains (additional_owned_domains). Send only the fields to change; unknown fields are rejected, and a request is applied whole or not at all. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background, and an additional_owned_domains change reprocesses the past answers that cite an added or removed domain (rematching=true); further edits are rejected while that runs. Only the account owner can send additional_owned_domains: a team member key gets ERR_INSUFFICIENT_PERMISSION and nothing is applied. prompt_limit sets or (null) removes the project's own prompt cap, as in Account Settings > Prompt Limits. Only the account owner or a co-owner whose permissions grant Projects update can send it (Account Settings > Prompt Limits lets any co-owner change it; here a co-owner, like every team member, also needs Projects update): any other team member gets ERR_INSUFFICIENT_PERMISSION, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with nothing applied. A request that sends only prompt_limit is applied even while a rematch runs. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** |  |  |
| **updateProjectRequest** | [**UpdateProjectRequest**](UpdateProjectRequest.md) |  |  |

### Return type

[**ProjectUpdateResponse**](ProjectUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **403** | A write with a read-only key answers ERR_INSUFFICIENT_SCOPE. A team member whose permissions do not grant Projects update (a co-owner included), who sends additional_owned_domains, or who sends prompt_limit without being a co-owner answers ERR_INSUFFICIENT_PERMISSION. A key limited to some projects that sends prompt_limit answers ERR_KEY_PROJECT_SCOPED. All with the same status, and nothing in the request is applied |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

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
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


# LLMPulse.SDK.Api.CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCompetitor**](CompetitorsApi.md#createcompetitor) | **POST** /competitors | Add a competitor |
| [**DeleteCompetitor**](CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**GetCompetitorDetails**](CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**ListCompetitorSuggestions**](CompetitorsApi.md#listcompetitorsuggestions) | **GET** /competitors/suggestions | List competitor suggestions |
| [**ListCompetitors**](CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors |
| [**UpdateCompetitor**](CompetitorsApi.md#updatecompetitor) | **PATCH** /competitors/{id} | Update a competitor |

<a id="createcompetitor"></a>
# **CreateCompetitor**
> CompetitorCreateResponse CreateCompetitor (CreateCompetitorRequest createCompetitorRequest)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md) |  |  |

### Return type

[**CompetitorCreateResponse**](CompetitorCreateResponse.md)

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

<a id="deletecompetitor"></a>
# **DeleteCompetitor**
> void DeleteCompetitor (int projectId, int id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a `read_write` scope API key.


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

<a id="getcompetitordetails"></a>
# **GetCompetitorDetails**
> CompetitorDetails GetCompetitorDetails (int projectId, int id)

Competitor details


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **int** |  |  |

### Return type

[**CompetitorDetails**](CompetitorDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitor details |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcompetitorsuggestions"></a>
# **ListCompetitorSuggestions**
> CompetitorSuggestionsResponse ListCompetitorSuggestions (int projectId, string basis = null, string query = null, int page = null, int perPage = null, string output = null)

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. `basis=brands` (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (`mentions`). `basis=citations` returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (`citations`). `discovery` tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **basis** | **string** |  | [optional] [default to brands] |
| **query** | **string** | Only suggestions whose brand name or domain contains this text | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**CompetitorSuggestionsResponse**](CompetitorSuggestionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcompetitors"></a>
# **ListCompetitors**
> ListCompetitors200Response ListCompetitors (int projectId, bool includeProjectBrand = null, string output = null)

List competitors


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **includeProjectBrand** | **bool** | When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional] [default to false] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitors |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updatecompetitor"></a>
# **UpdateCompetitor**
> void UpdateCompetitor (int id, UpdateCompetitorRequest updateCompetitorRequest)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** |  |  |
| **updateCompetitorRequest** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md) |  |  |

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
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


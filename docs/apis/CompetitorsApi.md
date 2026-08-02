# LLMPulse.SDK.Api.CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCompetitor**](CompetitorsApi.md#createcompetitor) | **POST** /competitors | Add a competitor |
| [**DeleteCompetitor**](CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**UpdateCompetitor**](CompetitorsApi.md#updatecompetitor) | **PATCH** /competitors/{id} | Update a competitor |

<a id="createcompetitor"></a>
# **CreateCompetitor**
> void CreateCompetitor (CreateCompetitorRequest createCompetitorRequest)

Add a competitor

Adds a competitor (brand name + domain) to a project. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md) |  |  |

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

<a id="deletecompetitor"></a>
# **DeleteCompetitor**
> void DeleteCompetitor (int projectId, int id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a `read_write` scope API key.


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

<a id="updatecompetitor"></a>
# **UpdateCompetitor**
> void UpdateCompetitor (int id, UpdateCompetitorRequest updateCompetitorRequest)

Update a competitor

Updates brand_name, matching_names (full replacement list; the brand name is always included automatically) and/or color. The domain is immutable after creation. Name changes re-run mention/citation matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.


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


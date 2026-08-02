# LLMPulse.SDK.Api.HealthApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Ping**](HealthApi.md#ping) | **GET** /ping | Health check |

<a id="ping"></a>
# **Ping**
> Ping200Response Ping (int projectId = null)

Health check

Validates the API key and optionally pings a project. Returns the authenticated user_id, project (if project_id is supplied), and a request_id.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Optional project to verify access for | [optional]  |

### Return type

[**Ping200Response**](Ping200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | API is healthy |  -  |
| **401** | Authentication failed |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


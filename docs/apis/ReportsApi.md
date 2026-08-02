# LLMPulse.SDK.Api.ReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTechnicalGeoReports**](ReportsApi.md#createtechnicalgeoreports) | **POST** /technical_geo_reports | Run technical GEO analysis |

<a id="createtechnicalgeoreports"></a>
# **CreateTechnicalGeoReports**
> void CreateTechnicalGeoReports (CreateTechnicalGeoReportsRequest createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createTechnicalGeoReportsRequest** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md) |  |  |

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


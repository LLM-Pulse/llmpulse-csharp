# LLMPulse.SDK.Api.SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetSearchConsolePages**](SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**GetSearchConsoleQueries**](SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**GetSearchConsoleSummary**](SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**GetSearchConsoleTimeseries**](SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |

<a id="getsearchconsolepages"></a>
# **GetSearchConsolePages**
> void GetSearchConsolePages (int projectId, int range = null, DateTime from = null, DateTime to = null, string sort = null, int page = null, int perPage = null, string output = null)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **sort** | **string** |  | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

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
| **200** | Top pages |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsolequeries"></a>
# **GetSearchConsoleQueries**
> void GetSearchConsoleQueries (int projectId, int range = null, DateTime from = null, DateTime to = null, string sort = null, int page = null, int perPage = null, string output = null)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Knowingly undercounts anonymized queries; for exact totals use /search_console/summary. Requires a connected Search Console property (Growth+).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **sort** | **string** |  | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

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
| **200** | Top queries |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsolesummary"></a>
# **GetSearchConsoleSummary**
> void GetSearchConsoleSummary (int projectId, int range = null, DateTime from = null, DateTime to = null, string dimension = null)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension=country or dimension=device to also receive the breakdown aggregated over the range. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **dimension** | **string** | Optional breakdown aggregated over the range | [optional]  |

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
| **200** | Search Console summary |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsoletimeseries"></a>
# **GetSearchConsoleTimeseries**
> void GetSearchConsoleTimeseries (int projectId, int range = null, DateTime from = null, DateTime to = null, string granularity = null, string output = null)

Search Console time series (Growth+)

Google Search Console property-wide series (impressions, clicks, ctr, position) bucketed by day, week or month. Requires a connected Search Console property (Growth+).


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

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
| **200** | Search Console time series |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


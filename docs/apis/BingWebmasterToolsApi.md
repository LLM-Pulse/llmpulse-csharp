# LLMPulse.SDK.Api.BingWebmasterToolsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetBingWebmasterPages**](BingWebmasterToolsApi.md#getbingwebmasterpages) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**GetBingWebmasterQueries**](BingWebmasterToolsApi.md#getbingwebmasterqueries) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**GetBingWebmasterSummary**](BingWebmasterToolsApi.md#getbingwebmastersummary) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**GetBingWebmasterTimeseries**](BingWebmasterToolsApi.md#getbingwebmastertimeseries) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |

<a id="getbingwebmasterpages"></a>
# **GetBingWebmasterPages**
> BingWebmasterListResponse GetBingWebmasterPages (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string sort = null, int page = null, int perPage = null, string output = null)

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project's connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional]  |
| **sort** | **string** | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top pages |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getbingwebmasterqueries"></a>
# **GetBingWebmasterQueries**
> BingWebmasterListResponse GetBingWebmasterQueries (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string sort = null, int page = null, int perPage = null, string output = null)

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project's connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional]  |
| **sort** | **string** | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top queries |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getbingwebmastersummary"></a>
# **GetBingWebmasterSummary**
> BingWebmasterSummaryResponse GetBingWebmasterSummary (int projectId, int range = null, DateOnly from = null, DateOnly to = null)

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences > Project Settings > Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional]  |

### Return type

[**BingWebmasterSummaryResponse**](BingWebmasterSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools summary |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getbingwebmastertimeseries"></a>
# **GetBingWebmasterTimeseries**
> BingWebmasterTimeseriesResponse GetBingWebmasterTimeseries (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string granularity = null, string output = null)

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**BingWebmasterTimeseriesResponse**](BingWebmasterTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools time series |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


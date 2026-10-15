# LLMPulse.SDK.Api.SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetSearchConsolePages**](SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**GetSearchConsoleQueries**](SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**GetSearchConsoleRows**](SearchConsoleApi.md#getsearchconsolerows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+) |
| [**GetSearchConsoleSummary**](SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**GetSearchConsoleTimeseries**](SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |

<a id="getsearchconsolepages"></a>
# **GetSearchConsolePages**
> SearchConsoleListResponse GetSearchConsolePages (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string sort = null, int page = null, int perPage = null, int startRow = null, string output = null, string searchType = null, string filters = null, string dataState = null, string aggregationType = null)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional]  |
| **sort** | **string** |  | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **startRow** | **int** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |
| **searchType** | **string** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to web] |
| **filters** | **string** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional]  |
| **dataState** | **string** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to final] |
| **aggregationType** | **string** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to auto] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

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
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsolequeries"></a>
# **GetSearchConsoleQueries**
> SearchConsoleListResponse GetSearchConsoleQueries (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string sort = null, int page = null, int perPage = null, int startRow = null, string output = null, string searchType = null, string filters = null, string dataState = null, string aggregationType = null)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional]  |
| **sort** | **string** |  | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **startRow** | **int** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |
| **searchType** | **string** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to web] |
| **filters** | **string** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional]  |
| **dataState** | **string** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to final] |
| **aggregationType** | **string** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to auto] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

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
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsolerows"></a>
# **GetSearchConsoleRows**
> SearchConsoleRowsResponse GetSearchConsoleRows (int projectId, string dimensions, int range = null, DateOnly from = null, DateOnly to = null, string sort = null, int page = null, int perPage = null, int startRow = null, string output = null, string searchType = null, string filters = null, string dataState = null, string aggregationType = null)

Search Console rows by several dimensions (Growth+)

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **dimensions** | **string** | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance. Each becomes a field of every row; country and device values are lowercase. |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional]  |
| **sort** | **string** |  | [optional] [default to impressions] |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **startRow** | **int** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional] [default to 0] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |
| **searchType** | **string** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to web] |
| **filters** | **string** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional]  |
| **dataState** | **string** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to final] |
| **aggregationType** | **string** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to auto] |

### Return type

[**SearchConsoleRowsResponse**](SearchConsoleRowsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console rows |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsolesummary"></a>
# **GetSearchConsoleSummary**
> SearchConsoleSummaryResponse GetSearchConsoleSummary (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string dimension = null, int limit = null, string searchType = null, string filters = null, string dataState = null, string aggregationType = null)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension=country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit. With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google's 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional]  |
| **dimension** | **string** | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. | [optional]  |
| **limit** | **int** | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. | [optional]  |
| **searchType** | **string** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to web] |
| **filters** | **string** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional]  |
| **dataState** | **string** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to final] |
| **aggregationType** | **string** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to auto] |

### Return type

[**SearchConsoleSummaryResponse**](SearchConsoleSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console summary |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getsearchconsoletimeseries"></a>
# **GetSearchConsoleTimeseries**
> SearchConsoleTimeseriesResponse GetSearchConsoleTimeseries (int projectId, int range = null, DateOnly from = null, DateOnly to = null, string granularity = null, string output = null, string searchType = null, string filters = null, string dataState = null, string aggregationType = null)

Search Console time series (Growth+)

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional]  |
| **from** | **DateOnly** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **to** | **DateOnly** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional]  |
| **granularity** | **string** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |
| **searchType** | **string** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional] [default to web] |
| **filters** | **string** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional]  |
| **dataState** | **string** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional] [default to final] |
| **aggregationType** | **string** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional] [default to auto] |

### Return type

[**SearchConsoleTimeseriesResponse**](SearchConsoleTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console time series |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


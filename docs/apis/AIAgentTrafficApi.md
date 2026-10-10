# LLMPulse.SDK.Api.AIAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAgentTraffic**](AIAgentTrafficApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**GetAiTraffic**](AIAgentTrafficApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**GetWebAnalyticsSchema**](AIAgentTrafficApi.md#getwebanalyticsschema) | **GET** /web_analytics/schema | Web analytics query format (Growth+) |
| [**ListAgentBots**](AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |
| [**QueryWebAnalytics**](AIAgentTrafficApi.md#querywebanalytics) | **POST** /web_analytics/query | Live web analytics query (Growth+) |

<a id="getagenttraffic"></a>
# **GetAgentTraffic**
> AgentTrafficResponse GetAgentTraffic (int projectId, int range = null, DateTime from = null, DateTime to = null, string bot = null, string company = null, string groupBy = null, string granularity = null)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project's origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **bot** | **string** | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional]  |
| **company** | **string** | Filter by company (e.g. openai, anthropic, google) | [optional]  |
| **groupBy** | **string** |  | [optional] [default to bot] |
| **granularity** | **string** |  | [optional]  |

### Return type

[**AgentTrafficResponse**](AgentTrafficResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getaitraffic"></a>
# **GetAiTraffic**
> void GetAiTraffic (int projectId, int range = null, DateTime from = null, DateTime to = null, string source = null, string granularity = null)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible, Matomo or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **source** | **string** | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional]  |
| **granularity** | **string** |  | [optional]  |

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
| **200** | AI referral traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getwebanalyticsschema"></a>
# **GetWebAnalyticsSchema**
> WebAnalyticsSchemaResponse GetWebAnalyticsSchema (int projectId)

Web analytics query format (Growth+)

How to query the web analytics provider connected to the project, live: the provider, the property every query runs on, the native query format it accepts, the allowed top-level fields, the rules the bridge enforces (the connected property is always used, only reads run, row limits), a worked example and, where the provider offers it, its live field list. Cached for an hour. Supported providers: Google Analytics 4, Adobe Analytics or Customer Journey Analytics, Matomo, PostHog, Plausible and Piano, connected on the AI Traffic page. Requires the Growth plan or above; otherwise ERR_PLAN_REQUIRED. Without a connected provider returns ERR_WEB_ANALYTICS_NOT_CONNECTED (404); a provider that refuses the stored credentials returns ERR_WEB_ANALYTICS_ACCESS_REVOKED (403); an unavailable provider, an exhausted provider quota, more than 20 uncached queries a minute or too many running at once for the project returns ERR_WEB_ANALYTICS_UPSTREAM (503): wait for the number of seconds in Retry-After before retrying.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |

### Return type

[**WebAnalyticsSchemaResponse**](WebAnalyticsSchemaResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Query format for the connected provider |  -  |
| **403** | Access forbidden |  -  |
| **404** | Resource not found |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds to wait before retrying: Google&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listagentbots"></a>
# **ListAgentBots**
> AgentBotsResponse ListAgentBots (int projectId, string output = null)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**AgentBotsResponse**](AgentBotsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bot catalog |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="querywebanalytics"></a>
# **QueryWebAnalytics**
> WebAnalyticsQueryResponse QueryWebAnalytics (QueryWebAnalyticsRequest queryWebAnalyticsRequest)

Live web analytics query (Growth+)

Runs a read-only query, written in the connected provider's native format, against the project's property and returns columns and rows: a GA4 Data API runReport body, an Adobe Analytics or Customer Journey Analytics report request, Matomo Reporting API parameters (get methods only), PostHog HogQL, a Plausible Stats API v2 query or a Piano getData body. The connected property, site, report suite or project is always used and any property field in the query is ignored. Rows default to 100 and are capped at 5,000. Identical queries are answered from a 10-minute cache (cached: true). A query the provider rejects returns ERR_WEB_ANALYTICS_INVALID_QUERY (422) with the provider's own validation message. Each uncached query spends the customer's provider API quota. A read: no writable key is needed. Supported providers: Google Analytics 4, Adobe Analytics or Customer Journey Analytics, Matomo, PostHog, Plausible and Piano, connected on the AI Traffic page. Requires the Growth plan or above; otherwise ERR_PLAN_REQUIRED. Without a connected provider returns ERR_WEB_ANALYTICS_NOT_CONNECTED (404); a provider that refuses the stored credentials returns ERR_WEB_ANALYTICS_ACCESS_REVOKED (403); an unavailable provider, an exhausted provider quota, more than 20 uncached queries a minute or too many running at once for the project returns ERR_WEB_ANALYTICS_UPSTREAM (503): wait for the number of seconds in Retry-After before retrying.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **queryWebAnalyticsRequest** | [**QueryWebAnalyticsRequest**](QueryWebAnalyticsRequest.md) |  |  |

### Return type

[**WebAnalyticsQueryResponse**](WebAnalyticsQueryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Query result as columns and rows |  -  |
| **403** | Access forbidden |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds to wait before retrying: Google&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage <br>  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


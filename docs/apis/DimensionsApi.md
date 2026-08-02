# LLMPulse.SDK.Api.DimensionsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetCompetitorDetails**](DimensionsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**GetProjectDetails**](DimensionsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details |
| [**ListAgentBots**](DimensionsApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale+) |
| [**ListAllCitations**](DimensionsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor) |
| [**ListAllMentions**](DimensionsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor) |
| [**ListCitations**](DimensionsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations |
| [**ListCollections**](DimensionsApi.md#listcollections) | **GET** /dimensions/collections | List tags/collections |
| [**ListCompetitorCitations**](DimensionsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations |
| [**ListCompetitorMentions**](DimensionsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions |
| [**ListCompetitors**](DimensionsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors |
| [**ListLocales**](DimensionsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data |
| [**ListMentions**](DimensionsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions |
| [**ListModels**](DimensionsApi.md#listmodels) | **GET** /dimensions/models | List models with data |
| [**ListProjects**](DimensionsApi.md#listprojects) | **GET** /dimensions/projects | List projects |
| [**ListPromptExecutions**](DimensionsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**ListPrompts**](DimensionsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts |
| [**ListSentimentCategories**](DimensionsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories |
| [**ListSources**](DimensionsApi.md#listsources) | **GET** /dimensions/sources | List source URLs |
| [**ListTags**](DimensionsApi.md#listtags) | **GET** /dimensions/tags | List tags (alias for /collections) |

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

<a id="getprojectdetails"></a>
# **GetProjectDetails**
> ProjectDetails GetProjectDetails (int id)

Project details

Detailed info for one project: matching_names, industry, business model, primary products, target audience, brand voice, locale, app store IDs, stats (incl. prompts_by_brand_kind counts) and data_coverage (models, countries and languages with data).


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

<a id="listagentbots"></a>
# **ListAgentBots**
> AgentBotsResponse ListAgentBots (int projectId, string output = null)

AI bot catalog (Scale+)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on all plans.


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

<a id="listallcitations"></a>
# **ListAllCitations**
> void ListAllCitations (int projectId, string competitors = null, int page = null, int perPage = null, string model = null, int collectionId = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List all citations (brand + competitor)

Unified citations stream with an `actor_type` field on each record. Includes visible citations and background source references; background references use position 0, meaning no visible rank.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated citations with actor_type discriminator |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listallmentions"></a>
# **ListAllMentions**
> void ListAllMentions (int projectId, string competitors = null, int page = null, int perPage = null, string model = null, int collectionId = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List all mentions (brand + competitor)

Unified mentions stream. Each record has an `actor_type` field (`project` or `competitor`) so the same payload covers both.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated mentions with actor_type discriminator |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcitations"></a>
# **ListCitations**
> void ListCitations (int projectId, int page = null, int perPage = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List brand citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated brand citations |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcollections"></a>
# **ListCollections**
> void ListCollections (int projectId, string output = null)

List tags/collections


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Collections |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcompetitorcitations"></a>
# **ListCompetitorCitations**
> void ListCompetitorCitations (int projectId, string competitors = null, int page = null, int perPage = null, string model = null, int collectionId = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List competitor citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated competitor citations |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listcompetitormentions"></a>
# **ListCompetitorMentions**
> void ListCompetitorMentions (int projectId, string competitors = null, int page = null, int perPage = null, string model = null, int collectionId = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List competitor mentions


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated competitor mentions |  -  |

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

<a id="listlocales"></a>
# **ListLocales**
> void ListLocales (int projectId)

List locales with data


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Locales |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmentions"></a>
# **ListMentions**
> void ListMentions (int projectId, int page = null, int perPage = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null, string output = null)

List brand mentions


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated brand mentions |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listmodels"></a>
# **ListModels**
> void ListModels (int projectId)

List models with data


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


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

<a id="listpromptexecutions"></a>
# **ListPromptExecutions**
> void ListPromptExecutions (int projectId, int page = null, int perPage = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null, string mentionFilter = null, string citationFilter = null, string competitors = null, string output = null)

List prompt executions


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **mentionFilter** | **string** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional]  |
| **citationFilter** | **string** | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional]  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated executions |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listprompts"></a>
# **ListPrompts**
> void ListPrompts (int projectId, int page = null, int perPage = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, string promptType = null, string brandKind = null, DateTime from = null, DateTime to = null, string output = null)

List prompts


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **promptType** | **string** | Filter by prompt type (search intent) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated prompts |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsentimentcategories"></a>
# **ListSentimentCategories**
> void ListSentimentCategories (int projectId, string output = null)

List sentiment categories

Sentiment metric keys + labels + colors. For records, use /sentiments.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Sentiment buckets |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listsources"></a>
# **ListSources**
> void ListSources (int projectId, int page = null, int perPage = null, string model = null, int collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, DateTime from = null, DateTime to = null, string sourceType = null, string mentionFilter = null, string competitors = null, string output = null)

List source URLs


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **int** |  | [optional]  |
| **countryCode** | **string** | ISO country code (e.g. US, GB, DE) | [optional]  |
| **languageCode** | **string** | ISO language code (e.g. en, es, de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** |  | [optional]  |
| **sourceType** | **string** | Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. | [optional]  |
| **mentionFilter** | **string** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional]  |
| **competitors** | **string** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sources |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listtags"></a>
# **ListTags**
> void ListTags (int projectId, string output = null)

List tags (alias for /collections)


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tags |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


# LLMPulse.SDK.Api.ShoppingAdsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListAds**](ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements |
| [**ListShopping**](ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results |

<a id="listads"></a>
# **ListAds**
> void ListAds (int projectId, int page = null, int perPage = null, string view = null, bool owned = null, string order = null, string direction = null, string query = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, string promptType = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null, string output = null)

List AI ad placements

Paid placements returned inside AI answers. view=advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view=ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **view** | **string** | Row shape: one per advertising domain, or one per placement | [optional] [default to advertisers] |
| **owned** | **bool** | Return only placements identified as the tracked brand&#39;s own (view&#x3D;ads) | [optional]  |
| **order** | **string** | Sort field; the allowed set depends on view | [optional]  |
| **direction** | **string** | Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [optional]  |
| **query** | **string** | Case-insensitive substring filter on the ad title, domain or snippet | [optional]  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
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
| **200** | Paginated ad rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listshopping"></a>
# **ListShopping**
> void ListShopping (int projectId, int page = null, int perPage = null, string view = null, bool owned = null, string order = null, string direction = null, string query = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, int prompt = null, string promptType = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null, string output = null)

List shopping results

Product cards returned inside AI answers. view=products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view=merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **view** | **string** | Row shape: one per distinct product, or one per merchant | [optional] [default to products] |
| **owned** | **bool** | Return only products identified as the tracked brand&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [optional]  |
| **order** | **string** | Sort field; the allowed set depends on view | [optional]  |
| **direction** | **string** |  | [optional] [default to desc] |
| **query** | **string** | Case-insensitive substring filter on the product title | [optional]  |
| **model** | **string** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **prompt** | **int** | Filter by prompt ID | [optional]  |
| **promptType** | **string** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
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
| **200** | Paginated shopping rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


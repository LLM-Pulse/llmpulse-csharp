# LLMPulse.SDK.Api.OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#getownedmediaprofiles) | **GET** /projects/{id}/owned_media | Get a project&#39;s owned-media profiles |
| [**GetOwnedMediaSummary**](OwnedMediaCommunitiesApi.md#getownedmediasummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary |
| [**ListOwnedMedia**](OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**ListOwnedMediaCitingPrompts**](OwnedMediaCommunitiesApi.md#listownedmediacitingprompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item |
| [**ListRedditCitations**](OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**UpdateOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#updateownedmediaprofiles) | **PATCH** /projects/{id}/owned_media | Update a project&#39;s owned-media profiles |

<a id="getownedmediaprofiles"></a>
# **GetOwnedMediaProfiles**
> OwnedMediaProfilesResponse GetOwnedMediaProfiles (int id)

Get a project's owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings > Owned Media shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** | Project ID |  |

### Return type

[**OwnedMediaProfilesResponse**](OwnedMediaProfilesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profiles per platform and the editable settings |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED, and a team member whose permissions do not grant Owned Media ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getownedmediasummary"></a>
# **GetOwnedMediaSummary**
> OwnedMediaSummaryResponse GetOwnedMediaSummary (int projectId, string provider, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null)

Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives the platform citations (total), yours (your profiles and their content), your_profile and your_content apart, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes the difference (percent for counts, percentage points for share_pct, null when there is nothing to compare). weekly is the citations per week, yours against everyone else. by_model and by_country split every citation of the platform; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider=mobile_apps adds stores, the per-store totals, and has no content type or age; provider=overview returns platforms, one rollup per platform the caller can read, and no breakdowns. A team member also needs the YouTube Intelligence permission for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **provider** | **string** | The platform to summarize, or overview for every platform at once |  |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |

### Return type

[**OwnedMediaSummaryResponse**](OwnedMediaSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The KPI cards, comparison, weekly series and breakdowns |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media (or YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listownedmedia"></a>
# **ListOwnedMedia**
> OwnedMediaListResponse ListOwnedMedia (int projectId, string provider, int page = null, int perPage = null, string view = null, string store = null, bool owned = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null, string output = null)

List owned-media citations

Which owned-media content AI answers cite, by platform. `provider` is required. Each row carries a `yours` flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. view=own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. A team member also needs the YouTube Intelligence permission for provider=youtube. Requires the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **provider** | **string** | The platform to report on |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **view** | **string** | Row shape; the allowed set depends on provider | [optional]  |
| **store** | **string** | provider&#x3D;mobile_apps only | [optional] [default to google_play] |
| **owned** | **bool** | Return only rows belonging to the account&#39;s own connected profile | [optional]  |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**OwnedMediaListResponse**](OwnedMediaListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated owned-media rows |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media (or YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listownedmediacitingprompts"></a>
# **ListOwnedMediaCitingPrompts**
> OwnedMediaCitingPromptsResponse ListOwnedMediaCitingPrompts (int projectId, string provider, int page = null, int perPage = null, string url = null, string profile = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null, string output = null)

List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **provider** | **string** | The platform the item belongs to |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **url** | **string** | A post or video URL, or a profile or channel URL. Exclusive with profile | [optional]  |
| **profile** | **string** | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url | [optional]  |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
| **brandKind** | **string** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional]  |
| **range** | **int** | Number of days to look back (alternative to from/to) | [optional]  |
| **from** | **DateTime** |  | [optional]  |
| **to** | **DateTime** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional]  |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**OwnedMediaCitingPromptsResponse**](OwnedMediaCitingPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The item and a page of the answers that cited it |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media and Prompts (and YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listredditcitations"></a>
# **ListRedditCitations**
> void ListRedditCitations (int projectId, int page = null, int perPage = null, string view = null, string subreddit = null, string author = null, string status = null, bool owned = null, string brand = null, string order = null, string direction = null, string model = null, string collectionId = null, string countryCode = null, string languageCode = null, string brandKind = null, int range = null, DateTime from = null, DateTime to = null, string output = null)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view=subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view=authors returns one row per author; view=threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. view=breakdowns returns the figures behind Reddit Intelligence > Sentiment and breakdowns: citations is the number of Reddit citations after the filters, and each row is one slice, with breakdown (sentiment, model or country), key, count and pct, the share within its breakdown as the page charts it. Sentiment is that of the AI answer that cited Reddit, with all five labels (very_positive to very_negative) listed, zero included; order and direction do not apply. Requires the Growth plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **view** | **string** |  | [optional] [default to subreddits] |
| **subreddit** | **string** | Filter to one subreddit (name without the r/ prefix) | [optional]  |
| **author** | **string** | Filter to one Reddit author | [optional]  |
| **status** | **string** | view&#x3D;threads only | [optional]  |
| **owned** | **bool** | Return only subreddits/authors the account has claimed as its own | [optional]  |
| **brand** | **string** | Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional]  |
| **order** | **string** | Sort field; the allowed set depends on view, and view&#x3D;breakdowns accepts none | [optional]  |
| **direction** | **string** |  | [optional] [default to desc] |
| **model** | **string** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional]  |
| **collectionId** | **string** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional]  |
| **countryCode** | **string** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional]  |
| **languageCode** | **string** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional]  |
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
| **200** | Paginated Reddit rows |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updateownedmediaprofiles"></a>
# **UpdateOwnedMediaProfiles**
> OwnedMediaProfilesUpdateResponse UpdateOwnedMediaProfiles (int id, UpdateOwnedMediaProfilesRequest updateOwnedMediaProfilesRequest)

Update a project's owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings > Owned Media. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, YouTube Intelligence create to change the YouTube channel, and Projects update to change the extra profile or Reddit lists. Requires the Growth plan or above and a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** | Project ID |  |
| **updateOwnedMediaProfilesRequest** | [**UpdateOwnedMediaProfilesRequest**](UpdateOwnedMediaProfilesRequest.md) |  |  |

### Return type

[**OwnedMediaProfilesUpdateResponse**](OwnedMediaProfilesUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The profiles after the change |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED, a read-only key ERR_INSUFFICIENT_SCOPE, and a team member without the Owned Media create permission (or YouTube Intelligence create for the YouTube channel) ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)


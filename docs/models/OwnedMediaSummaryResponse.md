# LLMPulse.SDK.Model.OwnedMediaSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Provider** | **string** |  | [optional] 
**From** | **DateTime** |  | [optional] 
**To** | **DateTime** |  | [optional] 
**Connected** | **bool** | Whether a profile is claimed on the platform (on overview, on any platform) | [optional] 
**Kpis** | [**OwnedMediaKpis**](OwnedMediaKpis.md) |  | [optional] 
**Previous** | [**OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  | [optional] 
**Changes** | [**OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  | [optional] 
**Weekly** | [**List&lt;OwnedMediaWeek&gt;**](OwnedMediaWeek.md) |  | [optional] 
**ByModel** | [**List&lt;OwnedMediaModelShare&gt;**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview | [optional] 
**ByCountry** | [**List&lt;OwnedMediaCountryShare&gt;**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview | [optional] 
**ContentTypes** | [**List&lt;OwnedMediaContentTypeShare&gt;**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only | [optional] 
**AgeBuckets** | [**List&lt;OwnedMediaAgeBucketShare&gt;**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out | [optional] 
**Stores** | [**List&lt;OwnedMediaStoreTotals&gt;**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only | [optional] 
**Platforms** | [**List&lt;OwnedMediaPlatformRollup&gt;**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read | [optional] 
**Activity** | [**List&lt;OwnedMediaSummaryActivityPeriod&gt;**](OwnedMediaSummaryActivityPeriod.md) | All providers. One row per project tracking period that holds a run inside the window; provider&#x3D;overview has null yours and other, and provider&#x3D;reddit also returns positive, neutral and negative sentiment counts. Citation counts use the days of the selected date window only, so when the window starts mid-period the first period counts fewer days than the app chart, which reads it whole. A period whose runs all fell before from is left out, and a period with runs but no citation has zero | [optional] 
**SubredditActivity** | [**List&lt;RedditSubredditActivityPeriod&gt;**](RedditSubredditActivityPeriod.md) | provider&#x3D;reddit only. One row per subreddit and tracking period that holds a run inside the window; the top five subreddits are separate and Others has a null subreddit | [optional] 
**Positions** | [**List&lt;RedditPositionShare&gt;**](RedditPositionShare.md) | provider&#x3D;reddit only. Position distribution over the selected date window | [optional] 
**BrandShare** | [**List&lt;RedditBrandShare&gt;**](RedditBrandShare.md) | provider&#x3D;reddit only. Citation share among the tracked brand and competitors with cited mentions | [optional] 
**Replies** | [**TrustpilotReplies**](TrustpilotReplies.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


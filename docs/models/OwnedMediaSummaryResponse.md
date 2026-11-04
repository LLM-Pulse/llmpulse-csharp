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
**Activity** | [**List&lt;OwnedMediaSummaryActivityPeriod&gt;**](OwnedMediaSummaryActivityPeriod.md) | All providers. One row per actual project reporting period with runs; provider&#x3D;overview has null yours and other, and provider&#x3D;reddit also returns positive, neutral and negative sentiment counts. Citation counts use the selected date window, and periods with runs but no citation have zero | [optional] 
**SubredditActivity** | [**List&lt;RedditSubredditActivityPeriod&gt;**](RedditSubredditActivityPeriod.md) | provider&#x3D;reddit only. One row per subreddit and actual reporting period; the top five subreddits are separate and Others has a null subreddit | [optional] 
**Positions** | [**List&lt;RedditPositionShare&gt;**](RedditPositionShare.md) | provider&#x3D;reddit only. Position distribution over the selected date window | [optional] 
**BrandShare** | [**List&lt;RedditBrandShare&gt;**](RedditBrandShare.md) | provider&#x3D;reddit only. Citation share among the tracked brand and competitors with cited mentions | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


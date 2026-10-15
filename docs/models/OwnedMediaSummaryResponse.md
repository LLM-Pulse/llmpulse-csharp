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
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


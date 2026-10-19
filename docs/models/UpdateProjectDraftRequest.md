# LLMPulse.SDK.Model.UpdateProjectDraftRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Step** | **string** |  | 
**Name** | **string** |  | [optional] 
**BrandName** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**Industry** | **List&lt;string&gt;** |  | [optional] 
**MatchingNames** | **List&lt;string&gt;** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) | [optional] 
**ExternalIdentifier** | **string** |  | [optional] 
**Prompts** | **List&lt;string&gt;** |  | [optional] 
**Competitors** | **List&lt;Object&gt;** | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor&#39;s matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects | [optional] 
**YoutubeChannelUrl** | **string** |  | [optional] 
**InstagramProfileUrl** | **string** |  | [optional] 
**FacebookPageUrl** | **string** |  | [optional] 
**TiktokProfileUrl** | **string** |  | [optional] 
**AppStoreUrl** | **string** |  | [optional] 
**GooglePlayUrl** | **string** |  | [optional] 
**Suggest** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


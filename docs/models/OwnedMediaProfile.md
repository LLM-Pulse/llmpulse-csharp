# LLMPulse.SDK.Model.OwnedMediaProfile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Url** | **string** |  | [optional] 
**Handle** | **string** | The handle, page id, store app id, subreddit or username | [optional] 
**Kind** | **string** |  | [optional] 
**Main** | **bool** | True for the main profile of its platform (or store), false for an extra one | [optional] 
**Store** | **string** | google_play or app_store for an app; null elsewhere | [optional] 
**Name** | **string** |  | [optional] 
**AvatarUrl** | **string** |  | [optional] 
**ScrapeStatus** | **string** | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


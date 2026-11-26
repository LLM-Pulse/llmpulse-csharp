# LLMPulse.SDK.Model.SourceRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PromptExecutionId** | **int** |  | 
**Position** | **int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank | 
**SourceType** | **string** | owned (the project&#39;s domains), competitor or third_party | 
**IsGooglePlayLink** | **bool** |  | 
**IsAppStoreLink** | **bool** |  | 
**CreatedAt** | **DateTime** |  | 
**Domain** | **string** | Registrable domain of the cited URL | 
**Url** | **string** | Normalized cited URL (tracking parameters and fragment removed) | 
**UrlSha256** | **string** | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


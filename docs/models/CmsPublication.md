# LLMPulse.SDK.Model.CmsPublication

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**Platform** | **string** |  | [optional] 
**SiteUrl** | **string** |  | [optional] 
**Status** | **string** | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code | [optional] 
**Title** | **string** |  | [optional] 
**Slug** | **string** |  | [optional] 
**SourceUrl** | **string** | For an update task, the page the draft revises | [optional] 
**RemoteId** | **int** | WordPress post id of the draft | [optional] 
**RemoteStatus** | **string** | WordPress status of the post when the draft was created (draft) | [optional] 
**RemoteUrl** | **string** |  | [optional] 
**EditUrl** | **string** | The post&#39;s edit screen in the WordPress admin | [optional] 
**ErrorCode** | **string** | Why the send failed, for example reconnect_required, missing_capability, unreachable or rejected | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**SentAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.BingWebmasterListResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Site** | **string** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional] 
**SyncStatus** | **string** | State of the daily sync: pending, syncing, completed, failed or on_hold (the data already synced still answers, but stops updating until the site is reconnected) | [optional] 
**LastSyncedAt** | **DateTime** | When the site last synced. Null before its first sync, or while history_current is false. | [optional] 
**HistoryCurrent** | **bool** | False right after the site was changed and before its first sync. Until then data is empty and data_through is null. | [optional] 
**From** | **DateOnly** |  | [optional] 
**To** | **DateOnly** |  | [optional] 
**DataThrough** | **DateOnly** | The last week_ending synced for the site (the Friday that closes a Bing week) | [optional] 
**Page** | **int** |  | [optional] 
**PerPage** | **int** |  | [optional] 
**Total** | **int** | Distinct pages or queries found in the weeks of the window | [optional] 
**Sort** | **string** |  | [optional] 
**WeeksCovered** | **int** | Weeks with data whose week_ending falls in the window | [optional] 
**Data** | [**List&lt;BingWebmasterListResponseDataInner&gt;**](BingWebmasterListResponseDataInner.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


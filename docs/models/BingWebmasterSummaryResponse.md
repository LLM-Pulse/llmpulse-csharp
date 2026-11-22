# LLMPulse.SDK.Model.BingWebmasterSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Site** | **string** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional] 
**SyncStatus** | **string** | State of the daily sync: pending, syncing, completed, failed or on_hold. on_hold means Bing refused the stored API key or the site is no longer verified: the data already synced still answers but stops updating until the site is reconnected in Preferences &gt; Project Settings &gt; Connections. | [optional] 
**LastSyncedAt** | **DateTime** | When the site last synced. Null before its first sync, or while history_current is false. | [optional] 
**HistoryCurrent** | **bool** | False right after the site was changed and before its first sync. Until then the response holds no data and data_through is null. | [optional] 
**From** | **DateOnly** |  | [optional] 
**To** | **DateOnly** |  | [optional] 
**DataThrough** | **DateOnly** | The last day synced for the site. Later days are missing, not zero. | [optional] 
**Totals** | [**BingWebmasterMetrics**](BingWebmasterMetrics.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


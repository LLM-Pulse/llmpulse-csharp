# LLMPulse.SDK.Model.ProjectDetailsAllOfBingWebmaster
Bing Webmaster Tools site behind /bing_webmaster. connected means its endpoints answer; reconnect_required means Bing refused the stored API key or the site is no longer verified, so the endpoints still answer from the data already synced, which stops updating until the site is reconnected at connect_url; not_connected means they return ERR_BING_WEBMASTER_NOT_CONNECTED.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** |  | [optional] 
**Site** | **string** | The connected site (e.g. https://example.com/), null when not connected | [optional] 
**LastSyncedAt** | **DateTime** | When that site last synced, null before its first sync | [optional] 
**ConnectUrl** | **string** | The in-app page where the site is connected or reconnected (Preferences &gt; Project Settings &gt; Connections) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


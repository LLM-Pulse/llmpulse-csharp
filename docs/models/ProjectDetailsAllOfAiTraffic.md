# LLMPulse.SDK.Model.ProjectDetailsAllOfAiTraffic
Web analytics provider behind /metrics/ai_traffic and /web_analytics. connected means both answer; reconnect_required means the provider refused the stored access, so /metrics/ai_traffic still answers from synced data and /web_analytics returns ERR_WEB_ANALYTICS_ACCESS_REVOKED until it is reconnected at connect_url; not_connected means they return ERR_AI_TRAFFIC_NOT_CONNECTED and ERR_WEB_ANALYTICS_NOT_CONNECTED.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** |  | [optional] 
**Provider** | **string** | The connected provider (e.g. google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo, piano), null when not connected | [optional] 
**ConnectUrl** | **string** | The in-app AI Traffic page, where the provider is connected or reconnected | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


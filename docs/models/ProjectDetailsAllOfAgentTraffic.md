# LLMPulse.SDK.Model.ProjectDetailsAllOfAgentTraffic
Agent traffic source behind /metrics/agent_traffic. connected and reconnect_required (the source refused the stored access, so syncing stopped) both answer from stored data; imported means no live source is connected but imported logs answer; not_connected means it returns ERR_AGENT_TRAFFIC_NOT_CONNECTED.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** |  | [optional] 
**Provider** | **string** | The connected source (e.g. cloudflare_graphql, bunny_cdn, s3 or the log drain&#39;s provider), null without a live source | [optional] 
**ConnectUrl** | **string** | The in-app Agent Analytics page, where a source is connected or reconnected | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


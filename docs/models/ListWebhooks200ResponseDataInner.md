# LLMPulse.SDK.Model.ListWebhooks200ResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**ProjectId** | **int** |  | [optional] 
**EventType** | **string** |  | [optional] 
**TargetUrl** | **string** | The URL deliveries are sent to. A read-only API key receives only its scheme, host and any non-default port followed by &#x60;/…&#x60; (for example &#x60;https://hook.eu1.make.com/…&#x60;); a &#x60;read_write&#x60; scope key receives the full URL. | [optional] 
**Disabled** | **bool** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked, or when that API key is limited to some projects and no longer covers the subscription&#39;s project. Creating it again with the same project, event and URL replaces it with a new subscription and secret. | [optional] 
**FailureCount** | **int** |  | [optional] 
**LastDeliveredAt** | **DateTime** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


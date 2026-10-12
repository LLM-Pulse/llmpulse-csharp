# LLMPulse.SDK.Model.ListWebhooks200ResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**ProjectId** | **int** |  | [optional] 
**EventType** | **string** |  | [optional] 
**TargetUrl** | **string** |  | [optional] 
**Disabled** | **bool** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked. Creating it again with the same project, event and URL replaces it with a new subscription and secret. | [optional] 
**FailureCount** | **int** |  | [optional] 
**LastDeliveredAt** | **DateTime** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


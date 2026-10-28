# LLMPulse.SDK.Model.CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | A label to recognize the key, for example the customer it is for | 
**ProjectIds** | **List&lt;int&gt;** | The projects the key is limited to, at least one | 
**Scope** | **string** | read (default) only reads data; read_write can also create, change and delete within the key&#39;s projects | [optional] [default to ScopeEnum.Read]

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


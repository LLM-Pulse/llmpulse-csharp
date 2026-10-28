# LLMPulse.SDK.Model.ApiKeyInfo

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Name** | **string** |  | 
**Prefix** | **string** | The visible start of the token, to recognize the key. Never the secret itself. | 
**Scope** | **string** |  | 
**ProjectScoped** | **bool** | True when the key is limited to project_ids; false for an account-wide key. | 
**ProjectIds** | **List&lt;int&gt;** | The projects the key is limited to; empty for an account-wide key. | 
**CreatedAt** | **DateTime** |  | 
**LastUsedAt** | **DateTime** | Updated at most once a minute. | 
**RevokedAt** | **DateTime** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


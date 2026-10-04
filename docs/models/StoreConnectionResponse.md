# LLMPulse.SDK.Model.StoreConnectionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** | The store platform, e.g. shopify | 
**Domain** | **string** | The store domain as compared: lowercase, without scheme, www or path | 
**Ambiguous** | **bool** | True when several live projects match the store domain (for example one project per market). project is then null and the app asks the key holder to pick from candidates. | 
**Candidates** | [**List&lt;StoreConnectionResponseCandidatesInner&gt;**](StoreConnectionResponseCandidatesInner.md) | Every live project of the account, for a project picker | 
**Account** | [**StoreConnectionResponseAccount**](StoreConnectionResponseAccount.md) |  | 
**RequestId** | **string** |  | 
**Project** | [**StoreConnectionResponseProject**](StoreConnectionResponseProject.md) |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.AccountQuota
A consumable quota. limit and remaining are null when unlimited is true. For a key limited to some projects, prompts and intelligence_tasks carry no limit (and intelligence_tasks no used): only the capacity left.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Limit** | **int** |  | [optional] 
**Used** | **int** |  | [optional] 
**Remaining** | **int** |  | [optional] 
**Unlimited** | **bool** |  | [optional] 
**Period** | **string** | Reset window for quotas that reset (e.g. month) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


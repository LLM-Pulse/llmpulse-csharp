# LLMPulse.SDK.Model.AccountPitchQuota
Pitch projects created this calendar month (Europe/Madrid) against the monthly allowance, which pitch projects use instead of a project slot. limit and remaining are null when unlimited is true.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Limit** | **int** |  | [optional] 
**Used** | **int** |  | [optional] 
**Remaining** | **int** |  | [optional] 
**Unlimited** | **bool** |  | [optional] 
**Period** | **string** | Always month | [optional] 
**ResetsOn** | **DateOnly** | The first day of next month, when the allowance starts again | [optional] 
**Access** | **string** | Whether the account may create pitch projects. The account owner or an account admin (co-owner) requests access in Account Settings &gt; Pitch projects and our team reviews it; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0 | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


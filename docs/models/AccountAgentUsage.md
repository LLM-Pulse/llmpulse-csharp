# LLMPulse.SDK.Model.AccountAgentUsage
The share of this calendar month's allowance for the in-app AI assistant (Europe/Madrid) that the account's team has used, owner and members together; each embedded project has an allowance of its own, left out here. The allowance is published as a share only, never as an amount; longer questions and bigger analyses use more of it. Deleting conversations gives nothing back.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PercentUsed** | **int** | Whole percent used, rounded down, from 0 to 100; 100 means the allowance is spent and new questions wait until resets_on. null when unlimited is true | [optional] 
**Unlimited** | **bool** |  | [optional] 
**Included** | **bool** | Whether the plan includes the in-app AI assistant. false on a plan without it, where percent_used is 100 | [optional] 
**Period** | **string** | Always month | [optional] 
**ResetsOn** | **DateOnly** | The first day of next month, when the allowance starts again | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


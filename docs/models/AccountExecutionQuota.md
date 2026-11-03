# LLMPulse.SDK.Model.AccountExecutionQuota
The account's allowance of AI answers for the current tracking window: its prompt limit times its enabled AI models, plus 5% so prompts can be replaced during the window. Every scheduled run and every first run of a new prompt spends one answer per AI model, and deleting a prompt gives nothing back. When it is used up, new prompts wait until resets_at. limit and remaining are null when unlimited is true. For a key limited to some projects, only remaining and unlimited (the account-wide answers left), period and resets_at.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Limit** | **int** |  | [optional] 
**Used** | **int** |  | [optional] 
**Remaining** | **int** |  | [optional] 
**Unlimited** | **bool** |  | [optional] 
**Period** | **string** | The tracking window, from the account&#39;s tracking cadence (week runs Monday to Sunday) | [optional] 
**ResetsAt** | **DateTime** | When the next window starts and the allowance is full again (00:00 Europe/Madrid) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


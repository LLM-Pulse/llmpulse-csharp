# LLMPulse.SDK.Model.GetAccount200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Plan** | **string** | Plan key (starter, growth, scale, ...). Absent for a key limited to some projects. | [optional] 
**PlanName** | **string** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key). Absent for a key limited to some projects. | [optional] 
**TrackingFrequency** | **string** | How often prompts run (weekly, daily, monthly, ...) | [optional] 
**Role** | **string** | Whether the key belongs to the account owner or a team member | [optional] 
**ApiKeyProjectIds** | **List&lt;int&gt;** | The projects the calling API key is limited to; null for a key that sees the whole account, and for OAuth | [optional] 
**Subscription** | [**GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  | [optional] 
**Limits** | [**GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  | [optional] 
**RateLimits** | [**GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


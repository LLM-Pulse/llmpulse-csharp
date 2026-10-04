# LLMPulse.SDK.Model.AiOrdersUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Platform** | **string** |  | 
**Currency** | **string** | ISO 4217 code, e.g. EUR | 
**From** | **DateOnly** | First day of the window this push replaces | 
**To** | **DateOnly** | Last day of the window; at most 400 days after from | 
**Days** | [**List&lt;AiOrdersUpdateRequestDaysInner&gt;**](AiOrdersUpdateRequestDaysInner.md) |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


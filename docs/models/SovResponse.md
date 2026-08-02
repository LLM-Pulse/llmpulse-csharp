# LLMPulse.SDK.Model.SovResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Periods** | [**List&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window. | [optional] 
**OverTime** | [**List&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  | [optional] 
**Current** | [**List&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  | [optional] 
**Breakdown** | [**List&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  | [optional] 
**Others** | **List&lt;Object&gt;** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


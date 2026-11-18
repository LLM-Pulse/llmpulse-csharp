# LLMPulse.SDK.Model.AiModelDeclinedAnswersResponseChartInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Date** | **DateOnly** | First day of the tracking period | 
**Answers** | **int** | Finished runs of the model, declined ones included | [optional] 
**Declined** | **int** | Answers the model declined | [optional] 
**DeclineRate** | **decimal** |  | [optional] 
**SafetyFilter** | **int** | Answers declined by the model&#39;s own safety filters | [optional] 
**SafetyFilterRate** | **decimal** |  | [optional] 
**TopicRefusal** | **int** | Answers that declined the topic itself, such as tobacco, gambling or alcohol | [optional] 
**TopicRefusalRate** | **decimal** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.AiModelDeclinedAnswersResponseByPromptDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Answers** | **int** | Finished runs of the model, declined ones included | [optional] 
**Declined** | **int** | Answers the model declined | [optional] 
**DeclineRate** | **decimal** |  | [optional] 
**SafetyFilter** | **int** | Answers declined by the model&#39;s own safety filters | [optional] 
**SafetyFilterRate** | **decimal** |  | [optional] 
**TopicRefusal** | **int** | Answers that declined the topic itself, such as tobacco, gambling or alcohol | [optional] 
**TopicRefusalRate** | **decimal** |  | [optional] 
**PromptId** | **int** |  | [optional] 
**PromptText** | **string** |  | [optional] 
**LastDeclinedAt** | **DateTime** | When the prompt&#39;s latest declined answer of the window was created; null when none was declined | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.AiModelSentimentMatrixActor
An actor (the standard actor shape) with one net sentiment cell per model

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** |  | [optional] 
**Id** | **int** | Project id, or competitor id | [optional] 
**CompetitorId** | **int** | Null for the project, the competitor id otherwise | [optional] 
**Name** | **string** |  | [optional] 
**Domain** | **string** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] 
**TotalSentiments** | **int** | The actor&#39;s sentiment verdicts summed over the models | [optional] 
**Models** | [**Dictionary&lt;string, AiModelSentimentCell&gt;**](AiModelSentimentCell.md) | One cell per model, keyed by model | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


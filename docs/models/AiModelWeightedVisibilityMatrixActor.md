# LLMPulse.SDK.Model.AiModelWeightedVisibilityMatrixActor
An actor (the standard actor shape) with one AI Visibility Score cell per model

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** |  | [optional] 
**Id** | **int** | Project id, or competitor id | [optional] 
**CompetitorId** | **int** | Null for the project, the competitor id otherwise | [optional] 
**Name** | **string** |  | [optional] 
**Domain** | **string** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] 
**TotalWeightedVisibilityScore** | **decimal** | The actor&#39;s AI Visibility Score across the enabled models, its points there divided by the project&#39;s days with answers in them, so actors compare | [optional] 
**Models** | [**Dictionary&lt;string, AiModelWeightedVisibilityCell&gt;**](AiModelWeightedVisibilityCell.md) | One cell per model, keyed by model | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


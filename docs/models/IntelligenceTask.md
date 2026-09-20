# LLMPulse.SDK.Model.IntelligenceTask

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**PublicId** | **string** |  | [optional] 
**ProjectId** | **int** |  | [optional] 
**TaskType** | **string** |  | [optional] 
**Title** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**PromptId** | **int** |  | [optional] 
**PromptText** | **string** |  | [optional] 
**AgenticMode** | **bool** |  | [optional] 
**CustomTopic** | **string** |  | [optional] 
**UserInstructions** | **string** |  | [optional] 
**OutputLanguageCode** | **string** |  | [optional] 
**WordCount** | **int** |  | [optional] 
**ResultData** | **Object** | Only present when status&#x3D;&#39;completed&#39; | [optional] 
**ErrorMessage** | **string** |  | [optional] 
**EstimatedTime** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**ProcessedAt** | **DateTime** |  | [optional] 
**ManuallyEditedAt** | **DateTime** | When the content was last edited by hand; null while the output is as generated | [optional] 
**EditedByUserId** | **int** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


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
**ResultData** | **Object** | The generated content once status is completed; null before that. A product_listing task returns title, summary, description_html (p, ul, ol, li, strong, em, h3 and br only), faq (question and answer pairs), seo_title, seo_description, image_alts (image_id and alt), changes (field and reason) and labels | [optional] 
**ErrorMessage** | **string** |  | [optional] 
**EstimatedTime** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**ProcessedAt** | **DateTime** |  | [optional] 
**ManuallyEditedAt** | **DateTime** | When the content was last edited by hand; null while the output is as generated | [optional] 
**EditedByUserId** | **int** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


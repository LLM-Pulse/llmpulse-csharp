# LLMPulse.SDK.Model.IntelligenceTaskCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**TaskType** | **string** | product_listing is API-only: it needs product and returns ready-to-apply product page copy | 
**PromptId** | **int** | Not used by product_listing; send null or omit it | [optional] 
**CustomTopic** | **string** |  | [optional] 
**UserInstructions** | **string** |  | [optional] 
**OutputLanguageCode** | **string** |  | [optional] 
**ExistingContent** | **string** |  | [optional] 
**ExistingContentUrl** | **string** |  | [optional] 
**Product** | [**IntelligenceTaskProduct**](IntelligenceTaskProduct.md) |  | [optional] 
**PromptIds** | **List&lt;int&gt;** | product_listing only: up to 20 project prompts the copy should answer | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


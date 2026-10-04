# LLMPulse.SDK.Model.CatalogPromptSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Prompt** | **string** |  | 
**Status** | **string** | pending, accepted or rejected | 
**Source** | **string** | Always catalog | 
**Product** | [**CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  | 
**CreatedAt** | **DateTime** |  | 
**CountryCode** | **string** |  | 
**LanguageCode** | **string** |  | 
**PromptId** | **int** | The tracked prompt an accepted suggestion became; null until accepted | 
**AcceptedAt** | **DateTime** | When the suggestion was accepted; null until then | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


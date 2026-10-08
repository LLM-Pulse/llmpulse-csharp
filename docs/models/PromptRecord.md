# LLMPulse.SDK.Model.PromptRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PromptText** | **string** |  | 
**CollectionIds** | **List&lt;int&gt;** | Every tag the prompt belongs to | 
**Tags** | [**List&lt;TagRef&gt;**](TagRef.md) |  | 
**AppUrl** | **string** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | 
**CollectionId** | **int** | Primary tag, when the prompt has one | 
**CountryCode** | **string** |  | 
**LanguageCode** | **string** |  | 
**PromptType** | **string** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | 
**BrandKind** | **string** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | 
**LastExecutedAt** | **DateTime** | Null until the prompt has run | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


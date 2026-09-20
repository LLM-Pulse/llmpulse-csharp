# LLMPulse.SDK.Model.ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**Name** | **string** | Internal project label (sidebar, settings, admin) | [optional] 
**BrandName** | **string** | LLM-facing brand label (used in prompts and customer-facing charts). Defaults to &#x60;name&#x60; when not set. | [optional] 
**Url** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**MatchingNames** | **List&lt;string&gt;** |  | [optional] 
**Industry** | **string** |  | [optional] 
**BusinessModel** | **string** |  | [optional] 
**BusinessModelOther** | **string** | Set only when business_model is OTHER | [optional] 
**PrimaryProducts** | **List&lt;string&gt;** |  | [optional] 
**TargetAudience** | **string** |  | [optional] 
**BrandVoice** | **string** |  | [optional] 
**Goals** | **string** |  | [optional] 
**CountryCode** | **string** |  | [optional] 
**LanguageCode** | **string** |  | [optional] 
**Paused** | **bool** |  | [optional] 
**GooglePlayId** | **string** |  | [optional] 
**AppStoreId** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


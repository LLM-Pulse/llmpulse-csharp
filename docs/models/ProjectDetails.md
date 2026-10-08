# LLMPulse.SDK.Model.ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**Name** | **string** | Internal project label (sidebar, settings, admin) | [optional] 
**BrandName** | **string** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. | [optional] 
**Url** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**MatchingNames** | **List&lt;string&gt;** |  | [optional] 
**Industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape | [optional] 
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
**DataCoverage** | [**ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.ProjectProfile
The project name and profile, as PATCH /projects/{id} and the update_project MCP tool return them

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Name** | **string** |  | 
**MatchingNames** | **List&lt;string&gt;** |  | 
**AdditionalOwnedDomains** | **List&lt;string&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none | 
**BrandName** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**Industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape | [optional] 
**BusinessModel** | **string** |  | [optional] 
**BusinessModelOther** | **string** | Set only when business_model is OTHER | [optional] 
**TargetAudience** | **string** |  | [optional] 
**PrimaryProducts** | **List&lt;string&gt;** |  | [optional] 
**BrandVoice** | **string** |  | [optional] 
**Goals** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


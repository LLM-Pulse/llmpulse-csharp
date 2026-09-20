# LLMPulse.SDK.Model.UpdateProjectRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**BrandName** | **string** | Brand name used to detect mentions. Applies to future runs; it does not rewrite history | [optional] 
**Description** | **string** | What the brand does. Context for Recommendations and GEO Writer (Brand Book) | [optional] 
**Industry** | **string** | Single industry key (e.g. SAAS); unknown keys are rejected | [optional] 
**BusinessModel** | **string** | Business model key (e.g. B2B_SAAS); unknown keys are rejected | [optional] 
**BusinessModelOther** | **string** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional] 
**TargetAudience** | **string** | Who the brand sells to (Brand Book) | [optional] 
**BrandVoice** | **string** | Tone of voice guidance for generated content (Brand Book) | [optional] 
**Goals** | **string** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional] 
**PrimaryProducts** | **List&lt;string&gt;** | Full replacement list of the main products or services | [optional] 
**MatchingNames** | **List&lt;string&gt;** | FULL replacement list of the brand-name variants used to detect mentions; send every variant to keep | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


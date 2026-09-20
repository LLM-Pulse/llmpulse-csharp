# LLMPulse.SDK.Model.ProjectCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**WebsiteUrl** | **string** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. | 
**Name** | **string** |  | 
**MainCountry** | **string** |  | 
**MainLanguage** | **string** |  | 
**BrandName** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**Industry** | **List&lt;string&gt;** |  | [optional] 
**BusinessModel** | **string** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected | [optional] 
**BusinessModelOther** | **string** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional] 
**TargetAudience** | **string** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) | [optional] 
**BrandVoice** | **string** | Tone of voice guidance for generated content (Brand Book) | [optional] 
**Goals** | **string** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional] 
**PrimaryProducts** | **List&lt;string&gt;** | Main products or services | [optional] 
**MatchingNames** | **List&lt;string&gt;** |  | [optional] 
**Prompts** | **List&lt;string&gt;** |  | [optional] 
**Competitors** | [**List&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  | [optional] 
**OwnedMedia** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  | [optional] 
**UseSubdomain** | **bool** |  | [optional] [default to false]
**WeeklyEmailSubscribed** | **bool** |  | [optional] [default to false]
**ExternalIdentifier** | **string** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account | [optional] 
**ExecutePromptsImmediately** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


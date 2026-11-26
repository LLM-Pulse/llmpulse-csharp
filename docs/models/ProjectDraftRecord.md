# LLMPulse.SDK.Model.ProjectDraftRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**DraftId** | **string** | Draft id (draft_...) | 
**Status** | **string** | open, finalized or expired | 
**CurrentStep** | **string** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized | 
**StepsCompleted** | **List&lt;string&gt;** |  | 
**StepsRemaining** | **List&lt;string&gt;** | Required steps not submitted yet | 
**OptionalSteps** | **List&lt;string&gt;** | Steps the plan allows but finalize does not require (owned_media from Growth) | 
**Finalizable** | **bool** |  | 
**WebsiteUrl** | **string** |  | 
**MainCountry** | **string** |  | 
**MainLanguage** | **string** |  | 
**UseSubdomain** | **bool** |  | 
**Industry** | **List&lt;string&gt;** |  | 
**MatchingNames** | **List&lt;string&gt;** |  | 
**Prompts** | **List&lt;string&gt;** |  | 
**Competitors** | [**List&lt;ProjectDraftRecordCompetitorsInner&gt;**](ProjectDraftRecordCompetitorsInner.md) |  | 
**OwnedMedia** | [**ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  | 
**WeeklyEmailSubscribed** | **bool** |  | 
**ExecutePromptsImmediately** | **bool** |  | 
**ExpiresAt** | **DateTime** |  | 
**CreatedAt** | **DateTime** |  | 
**Name** | **string** | Null until the details step | 
**BrandName** | **string** |  | 
**Description** | **string** |  | 
**ExternalIdentifier** | **string** |  | 
**ProjectId** | **int** | The project the draft became; null until finalized | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


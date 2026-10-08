# LLMPulse.SDK.Model.ProjectCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**DraftId** | **string** | The finalized draft; only present on POST /project_drafts/{id}/finalize | [optional] 
**Project** | **Object** | Same shape as GET /dimensions/projects/{id} | [optional] 
**Prompts** | [**ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  | [optional] 
**Competitors** | [**ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  | [optional] 
**Collections** | [**List&lt;ProjectCreateResponseCollectionsInner&gt;**](ProjectCreateResponseCollectionsInner.md) | Collections created from the request&#39;s collections field (empty when none were sent; absent on an idempotent replay) | [optional] 
**SameDomainProjects** | [**List&lt;ProjectCreateResponseSameDomainProjectsInner&gt;**](ProjectCreateResponseSameDomainProjectsInner.md) | Projects the caller can already see on the same domain (absent on an idempotent replay). Informational only: the create is never blocked, since one domain tracked per market is a normal setup. | [optional] 
**EmailSubscription** | [**ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md) |  | [optional] 
**Limits** | [**ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md) |  | [optional] 
**Idempotent** | **bool** | Present and true only on external_identifier replays | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


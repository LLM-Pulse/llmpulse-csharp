# LLMPulse.SDK.Model.RecommendationItem
One recommendation item, in the shape GET /recommendations/{id} lists items

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**RecommendationId** | **int** |  | 
**RecommendationType** | **string** |  | 
**Category** | **string** |  | 
**Title** | **string** |  | 
**Priority** | **string** |  | 
**ActionItems** | **List&lt;string&gt;** |  | 
**SourceRefs** | **List&lt;string&gt;** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs | 
**Status** | **string** |  | 
**Position** | **int** |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**Description** | **string** |  | [optional] 
**EstimatedImpact** | **string** |  | [optional] 
**StatusChangedAt** | **DateTime** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**ResolvedSourceRefs** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** | The evidence each source_refs code points to (prompt, citation or own page) | [optional] 
**UnresolvedSourceRefs** | **List&lt;string&gt;** | Present only when a code points to no stored evidence | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


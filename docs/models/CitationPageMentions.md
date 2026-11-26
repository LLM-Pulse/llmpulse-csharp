# LLMPulse.SDK.Model.CitationPageMentions
The brands the cited page mentions, from its analysis for the requesting project. A page not yet analyzed for it has null brand_mentioned, competitor_mentioned and brand_position and empty lists.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ContentGapStatus** | **string** | missing_page_cache, content_unavailable, mentions_not_processed, mentioned, gap (a competitor but not the brand) or not_mentioned | 
**Brands** | [**List&lt;CitationPageMentionsBrandsInner&gt;**](CitationPageMentionsBrandsInner.md) | Each brand the page mentions once, in order of first mention | 
**BrandMentioned** | **bool** |  | 
**CompetitorMentioned** | **bool** |  | 
**BrandPosition** | **int** | Rank of the brand&#39;s first mention on the page; null when it has none | 
**Mentions** | [**List&lt;CitationPageMentionsMentionsInner&gt;**](CitationPageMentionsMentionsInner.md) | Every mention on the page with its snippet; not sent on GET /citation_intelligence/groups | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.CitationGroupRow
A cited URL, domain or host (view). url-view rows carry url, url_sha256 and normalized_url, plus page_cache and page_mentions when page details are included; domain and host rows carry domain or host and aggregate_details.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**SourceId** | **int** | The group&#39;s first citation | 
**View** | **string** | url, domain or host | 
**Key** | **string** | The URL as cited, the domain or the host | 
**TotalResponses** | **int** | Answers citing it | 
**TotalCitations** | **int** |  | 
**CitationRate** | **decimal** | total_responses as a percentage (0-100) of citation_rate_denominator | 
**CitationRateDenominator** | **int** | Answers matching the filters | 
**Models** | **Dictionary&lt;string, int&gt;** | Answers citing it per AI model, keyed by model | 
**AvgCitationPosition** | **decimal** | Null when no visible citation has a rank | 
**FirstSeenAt** | **DateTime** |  | 
**LastSeenAt** | **DateTime** |  | 
**Url** | **string** | url view only. The URL as cited | [optional] 
**UrlSha256** | **string** | url view only. Key of the cited page, shared by the URL&#39;s variants | [optional] 
**NormalizedUrl** | **string** | url view only | [optional] 
**PageCache** | [**CitationPageCache**](CitationPageCache.md) |  | [optional] 
**PageMentions** | [**CitationPageMentions**](CitationPageMentions.md) |  | [optional] 
**Domain** | **string** | domain view only | [optional] 
**Host** | **string** | host view only | [optional] 
**AggregateDetails** | [**CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md) |  | [optional] 
**CitationSeries** | [**CitationSeries**](CitationSeries.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


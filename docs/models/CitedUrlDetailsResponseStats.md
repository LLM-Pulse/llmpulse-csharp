# LLMPulse.SDK.Model.CitedUrlDetailsResponseStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**TotalResponses** | **int** | Answers citing the URL under the filters | 
**TotalCitations** | **int** |  | 
**CitationRate** | **decimal** | total_responses as a percentage (0-100) of citation_rate_denominator | 
**CitationRateDenominator** | **int** | Answers matching the filters | 
**DistinctUrls** | **int** | Spellings of the URL cited (tracking parameters, a trailing slash) | 
**SourceTypes** | [**CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  | 
**Models** | **Dictionary&lt;string, int&gt;** | Answers citing the URL per AI model, keyed by model | 
**AvgCitationPosition** | **decimal** | Null when no visible citation has a rank | 
**FirstSeenAt** | **DateTime** | Null when no citation matches the filters | 
**LastSeenAt** | **DateTime** | Null when no citation matches the filters | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


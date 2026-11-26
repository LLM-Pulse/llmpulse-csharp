# LLMPulse.SDK.Model.CitedUrlOccurrencesResponseAllOfData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**SourceId** | **int** |  | 
**AnswerId** | **int** |  | 
**PromptExecutionId** | **int** | Same as answer_id | 
**PromptId** | **int** |  | 
**PromptText** | **string** |  | 
**Model** | **string** |  | 
**CitationPosition** | **int** | Rank of the citation in the answer; 0 for a background source reference | 
**Url** | **string** | Normalized cited URL | 
**SourceType** | **string** | owned, competitor or third_party | 
**ResponseExcerpt** | **string** | The first 600 characters of the answer | 
**ResponseTruncated** | **bool** |  | 
**ExecutedAt** | **DateTime** |  | 
**Domain** | **string** |  | 
**FanOutQueries** | **List&lt;string&gt;** | Sub-queries the model issued while answering; null when the model reports none | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


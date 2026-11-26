# LLMPulse.SDK.Model.CitationPageCache
What was read on the cited page. Metadata is null when the page has no usable content.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Present** | **bool** | Whether the page has a saved copy | 
**MentionsProcessed** | **bool** | Whether the page&#39;s mention analysis has completed for this project | 
**ContentAvailable** | **bool** |  | 
**LastCrawledAt** | **DateTime** | When the saved copy was read; null without usable content | 
**StatusCode** | **int** | A saved successful response or an observed 404/410; null otherwise | 
**ErrorMessage** | **string** | Always null; crawl errors are not exposed | 
**ContentFormat** | **string** |  | 
**Bytes** | **int** |  | 
**HtmlTitle** | **string** |  | 
**MetaTitle** | **string** |  | 
**MetaDescription** | **string** |  | 
**H1** | **string** |  | 
**CanonicalUrl** | **string** |  | 
**Language** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


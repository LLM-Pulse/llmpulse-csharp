# LLMPulse.SDK.Model.PromptSummaryRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PromptId** | **int** |  | [optional] 
**PromptText** | **string** |  | [optional] 
**Model** | **string** | Only present when breakdown&#x3D;model | [optional] 
**Responses** | **int** |  | [optional] 
**Mentions** | **int** |  | [optional] 
**Citations** | **int** |  | [optional] 
**Visibility** | **decimal** |  | [optional] 
**MentionRate** | **decimal** |  | [optional] 
**CitationRate** | **decimal** |  | [optional] 
**AvgMentionPosition** | **decimal** |  | [optional] 
**AvgPosition** | **decimal** |  | [optional] 
**AppUrl** | **string** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | [optional] 
**CountryCode** | **string** | Country of the prompt, as in /dimensions/prompts | [optional] 
**LanguageCode** | **string** | Language of the prompt, as in /dimensions/prompts | [optional] 
**PromptType** | **string** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | [optional] 
**BrandKind** | **string** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | [optional] 
**Tags** | [**List&lt;TagRef&gt;**](TagRef.md) | Every tag the prompt belongs to | [optional] 
**SentimentResponses** | **int** | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) | [optional] 
**SentimentVeryPositive** | **decimal** | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 | [optional] 
**SentimentPositive** | **decimal** | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 | [optional] 
**SentimentNeutral** | **decimal** | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 | [optional] 
**SentimentNegative** | **decimal** | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 | [optional] 
**SentimentVeryNegative** | **decimal** | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 | [optional] 
**NetSentiment** | **decimal** | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


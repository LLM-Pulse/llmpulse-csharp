# LLMPulse.SDK.Model.AiModelSentimentRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Model** | **string** | AI model key, as /dimensions/models lists it | [optional] 
**Label** | **string** | Display name of the model | [optional] 
**Color** | **string** | Hex color the app charts the model with | [optional] 
**SentimentsCount** | **int** | Brand sentiment verdicts in the model&#39;s answers | [optional] 
**PositiveCount** | **int** | Positive and very positive verdicts | [optional] 
**NegativeCount** | **int** | Negative and very negative verdicts | [optional] 
**NetSentiment** | **decimal** | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


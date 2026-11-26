# LLMPulse.SDK.Model.AnswerRecord
One answer. Without query a row carries response and response_truncated; with query it carries snippet and match_count instead

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**PromptId** | **int** |  | 
**PromptText** | **string** |  | 
**Model** | **string** |  | 
**NoResult** | **bool** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | 
**MentionsCount** | **int** | Mentions of your brand in the answer | 
**CitationsCount** | **int** | Citations of your brand in the answer | 
**AppUrl** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | 
**ExecutedAt** | **DateTime** |  | 
**DurationMs** | **decimal** | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place | 
**NoResultReason** | **string** | Present only when no_result is true. declined &#x3D; the model declined to answer and response holds its reply; no_answer &#x3D; no answer could be collected | [optional] 
**Response** | **string** | The answer text, cut to 10,000 characters (without query) | [optional] 
**ResponseTruncated** | **bool** | Whether response was cut (without query) | [optional] 
**Snippet** | **string** | The text around the first match (with query) | [optional] 
**MatchCount** | **int** | Matches of query in the answer (with query) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


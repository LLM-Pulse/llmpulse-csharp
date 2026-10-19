# LLMPulse.SDK.Model.AnswerDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlanRequiredFields** | **List&lt;string&gt;** | The fields left out of this answer because the account&#39;s plan does not include them (sentiments below Growth, shopping_products below Scale). Always present, empty when nothing is left out | 
**Id** | **int** |  | [optional] 
**PromptId** | **int** |  | [optional] 
**PromptText** | **string** |  | [optional] 
**Model** | **string** |  | [optional] 
**Response** | **string** |  | [optional] 
**ResponseTruncated** | **bool** |  | [optional] 
**ExecutedAt** | **DateTime** |  | [optional] 
**DurationMs** | **decimal** | Milliseconds, rounded to one decimal place | [optional] 
**Success** | **bool** | Null while the answer is still pending | [optional] 
**NoResult** | **bool** | True for a sentinel non-answer (the provider returned nothing after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | [optional] 
**FanOutQueries** | **List&lt;string&gt;** |  | [optional] 
**Mentions** | **List&lt;Object&gt;** |  | [optional] 
**Citations** | **List&lt;Object&gt;** |  | [optional] 
**CompetitorMentions** | **List&lt;Object&gt;** |  | [optional] 
**CompetitorCitations** | **List&lt;Object&gt;** |  | [optional] 
**Sentiments** | **List&lt;Object&gt;** | Needs the Growth plan or above; left out below it and named in plan_required_fields | [optional] 
**Sources** | **List&lt;Object&gt;** |  | [optional] 
**ShoppingProducts** | **List&lt;Object&gt;** | Needs the Scale plan or above; left out below it and named in plan_required_fields | [optional] 
**BrandEntities** | **List&lt;Object&gt;** |  | [optional] 
**LocalBusinesses** | **List&lt;Object&gt;** |  | [optional] 
**Locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  | [optional] 
**AppUrl** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


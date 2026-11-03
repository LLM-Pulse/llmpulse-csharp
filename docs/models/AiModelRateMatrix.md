# LLMPulse.SDK.Model.AiModelRateMatrix
Each actor's rate within each model: mentions of the actor (mentions_market_share), or answers citing it (citations_market_share), per answer of the model. Rates are independent, so the actors of a model can add up to more or less than 100.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**DenominatorsByModel** | **Dictionary&lt;string, int&gt;** | Answers of each model in the window, keyed by model | [optional] 
**Actors** | [**List&lt;AiModelRateMatrixActor&gt;**](AiModelRateMatrixActor.md) | The project and each competitor with a mention (or citation) in the window (only the competitors given in competitors, when it is given), by total descending | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


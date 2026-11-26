# LLMPulse.SDK.Model.QueryFanOutRow
A view=query row carries query_text, count and share; a view=prompt row carries prompt_id, prompt_text, variations_count and total_count

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**QueryText** | **string** | The sub-query a model issued (view&#x3D;query) | [optional] 
**Count** | **int** | Times it was issued (view&#x3D;query) | [optional] 
**Share** | **decimal** | Share of all sub-query occurrences, on a 0-100 scale (view&#x3D;query) | [optional] 
**PromptId** | **int** | view&#x3D;prompt | [optional] 
**PromptText** | **string** | view&#x3D;prompt | [optional] 
**VariationsCount** | **int** | Distinct sub-queries issued for the prompt (view&#x3D;prompt) | [optional] 
**TotalCount** | **int** | Sub-queries issued for the prompt, repeats included (view&#x3D;prompt) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


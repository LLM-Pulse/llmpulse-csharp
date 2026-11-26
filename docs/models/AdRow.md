# LLMPulse.SDK.Model.AdRow
One row of /dimensions/ads. Fields depend on view: advertisers (domain, ads, executions, prompts, avg_position, best_position) and ads (id, model, title, snippet, url, domain, position, is_client, prompt_id, prompt_text, prompt_execution_id, executed_at).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Domain** | **string** | Advertising domain; null on a placement that names none (view&#x3D;ads) | 
**Ads** | **int** | Placements of the domain (view&#x3D;advertisers) | [optional] 
**Executions** | **int** | Answers that carried them (view&#x3D;advertisers) | [optional] 
**Prompts** | **int** | Distinct prompts that triggered them (view&#x3D;advertisers) | [optional] 
**AvgPosition** | **decimal** | Average position, 1 is the best slot; null when no placement has one (view&#x3D;advertisers) | [optional] 
**BestPosition** | **int** | Best position, 1 is the best slot (view&#x3D;advertisers) | [optional] 
**Id** | **int** | The placement (view&#x3D;ads) | [optional] 
**Model** | **string** |  | [optional] 
**Title** | **string** |  | [optional] 
**Snippet** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**Position** | **int** | Position of the placement, 1 is the best slot (view&#x3D;ads) | [optional] 
**IsClient** | **bool** | Whether the placement is identified as your brand&#39;s own (view&#x3D;ads) | [optional] 
**PromptId** | **int** |  | [optional] 
**PromptText** | **string** |  | [optional] 
**PromptExecutionId** | **int** |  | [optional] 
**ExecutedAt** | **DateTime** | When the answer that carried the placement was collected (view&#x3D;ads) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


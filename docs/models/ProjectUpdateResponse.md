# LLMPulse.SDK.Model.ProjectUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Project** | [**ProjectProfile**](ProjectProfile.md) |  | 
**UpdatedFields** | **List&lt;string&gt;** | The fields the request sent | 
**Rematching** | **bool** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes | 
**Note** | **string** | What the change does to mention detection, citation ownership and historical numbers, and, when prompt_limit was sent, how many prompts the project holds and how many more can be added | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


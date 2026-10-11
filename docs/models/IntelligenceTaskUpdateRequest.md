# LLMPulse.SDK.Model.IntelligenceTaskUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Edits** | **Dictionary&lt;string, string&gt;** | Dotted result_data paths (title, sections.0.content, key_points.2) mapped to their replacement text. Only string fields that already exist are editable; sections cannot be added or removed. | 
**ResultVersion** | **string** | Optional. The result_version of the task as last read. When sent, the edit is refused with ERR_STALE_CONTENT (409) and nothing is written if the task was regenerated since. Omitted, null or empty, the edits apply to whatever the task holds now | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.GeoAuditRunResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Sequence** | **int** | Run number within the audit, starting at 1 | [optional] 
**Status** | **string** |  | [optional] 
**Trigger** | **string** |  | [optional] 
**Score** | **decimal** |  | [optional] 
**Grade** | **string** |  | [optional] 
**ScoreDelta** | **decimal** | Score change against the previous completed run | [optional] 
**ComparableToPrevious** | **bool** | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change | [optional] 
**NewIssues** | **int** |  | [optional] 
**FixedIssues** | **int** |  | [optional] 
**RegressedIssues** | **int** |  | [optional] 
**Error** | **string** |  | [optional] 
**EngineVersion** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**FinishedAt** | **DateTime** |  | [optional] 
**AppUrl** | **string** |  | [optional] 
**ProjectId** | **int** |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


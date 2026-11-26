# LLMPulse.SDK.Model.QueryFanOutsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Page** | **int** |  | 
**PerPage** | **int** |  | 
**Total** | **int** | Rows matching the filters across every page | 
**RequestId** | **string** |  | 
**View** | **string** | query or prompt, the row shape of data | 
**Data** | [**List&lt;QueryFanOutRow&gt;**](QueryFanOutRow.md) |  | 
**TotalOccurrences** | **int** | Sub-query occurrences across every page (view&#x3D;query) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


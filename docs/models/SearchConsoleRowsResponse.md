# LLMPulse.SDK.Model.SearchConsoleRowsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] 
**From** | **DateOnly** |  | [optional] 
**To** | **DateOnly** |  | [optional] 
**DataThrough** | **DateOnly** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. | [optional] 
**Page** | **int** |  | [optional] 
**PerPage** | **int** |  | [optional] 
**Total** | **int** | Rows in this window (one Google request, at most 25,000) | [optional] 
**Sort** | **string** |  | [optional] 
**StartRow** | **int** | Present when start_row was set | [optional] 
**Truncated** | **bool** | Present (true) when Google returned 25,000 rows, so more rows exist past this window | [optional] 
**Dimensions** | **List&lt;string&gt;** |  | [optional] 
**Data** | [**List&lt;SearchConsoleRowsResponseDataInner&gt;**](SearchConsoleRowsResponseDataInner.md) | One row per combination; only the requested dimensions are present | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


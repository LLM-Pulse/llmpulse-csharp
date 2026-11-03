# LLMPulse.SDK.Model.SearchConsoleDecayResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] 
**Properties** | [**List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional] 
**ExcludedProperties** | [**List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional] 
**PropertyErrors** | [**List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional] 
**From** | **DateOnly** |  | [optional] 
**To** | **DateOnly** |  | [optional] 
**DataThrough** | **DateOnly** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional] 
**Dimension** | **string** |  | [optional] 
**ComparedThrough** | **DateOnly** | Last day of the requested window that is compared, to or the last day Google has published when that is earlier | [optional] 
**PreviousFrom** | **DateOnly** | Start of the window compared against, the same length as from..compared_through and just before it | [optional] 
**PreviousTo** | **DateOnly** |  | [optional] 
**MinClicks** | **int** |  | [optional] 
**Page** | **int** |  | [optional] 
**PerPage** | **int** |  | [optional] 
**Total** | **int** | Rows in the report before paging | [optional] 
**Truncated** | **bool** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only | [optional] 
**Data** | [**List&lt;SearchConsoleDecayResponseDataInner&gt;**](SearchConsoleDecayResponseDataInner.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


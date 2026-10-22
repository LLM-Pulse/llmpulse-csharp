# LLMPulse.SDK.Model.SearchConsoleTimeseriesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] 
**From** | **DateOnly** |  | [optional] 
**To** | **DateOnly** |  | [optional] 
**DataThrough** | **DateOnly** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional] 
**Granularity** | **string** |  | [optional] 
**Data** | [**List&lt;SearchConsoleTimeseriesResponseDataInner&gt;**](SearchConsoleTimeseriesResponseDataInner.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 
**Properties** | [**List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional] 
**ExcludedProperties** | [**List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional] 
**PropertyErrors** | [**List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


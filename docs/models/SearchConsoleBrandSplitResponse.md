# LLMPulse.SDK.Model.SearchConsoleBrandSplitResponse

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
**BrandTerms** | **List&lt;string&gt;** | The project&#39;s brand name, matching names, app names and domain, lowercased, each matched as a whole word | [optional] 
**Totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] 
**Branded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] 
**NonBranded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] 
**Unclassified** | [**SearchConsoleBrandSplitResponseUnclassified**](SearchConsoleBrandSplitResponseUnclassified.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


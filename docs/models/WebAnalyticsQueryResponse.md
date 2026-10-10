# LLMPulse.SDK.Model.WebAnalyticsQueryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Provider** | **string** |  | [optional] 
**Property** | **string** |  | [optional] 
**Columns** | [**List&lt;WebAnalyticsQueryResponseColumnsInner&gt;**](WebAnalyticsQueryResponseColumnsInner.md) |  | [optional] 
**Rows** | **List&lt;List&lt;Object&gt;&gt;** | One array per row, values in column order: strings, numbers or null. | [optional] 
**RowCount** | **int** | Rows in this response (at most 5,000). | [optional] 
**TotalRows** | **int** | Rows the provider has for the query, when it reports it. | [optional] 
**Truncated** | **bool** | True when the provider has more rows than returned; page with its own offset or page field. | [optional] 
**Totals** | **Dictionary&lt;string, Object&gt;** | Metric totals by metric name, when the query asked for them. | [optional] 
**Notes** | **List&lt;string&gt;** | Provider caveats: sampling, thresholds, more rows available. | [optional] 
**Meta** | **Dictionary&lt;string, Object&gt;** | Provider metadata such as GA4 time zone, currency and remaining property quota. | [optional] 
**FetchedAt** | **DateTime** | When the provider answered. | [optional] 
**Cached** | **bool** | True when the answer came from the 10-minute cache instead of the provider. | [optional] 
**Query** | **Dictionary&lt;string, Object&gt;** | The request as sent to the provider, with the connected property forced and limits applied. | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


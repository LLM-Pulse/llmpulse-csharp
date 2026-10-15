# LLMPulse.SDK.Model.CustomReportWidget

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Key** | **string** |  | 
**Label** | **string** |  | 
**Kind** | **string** |  | 
**Width** | **string** |  | 
**Available** | **bool** | false when the widget&#39;s data source (web analytics, agent analytics, owned media) is not connected | 
**Data** | **Dictionary&lt;string, Object&gt;** | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


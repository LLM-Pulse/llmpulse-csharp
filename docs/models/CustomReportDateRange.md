# LLMPulse.SDK.Model.CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** | rolling (the last range_days days) or previous_month (the previous calendar month) | 
**RangeDays** | **int** | Length of a rolling window; null for previous_month | 
**From** | **DateOnly** | First day of the window as of now (detail only) | [optional] 
**To** | **DateOnly** | Last day of the window as of now (detail only) | [optional] 
**Label** | **string** | The window as the report shows it (detail only) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


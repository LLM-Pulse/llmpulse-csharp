# LLMPulse.SDK.Model.CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) | 
**RangeDays** | **int** | Length of a rolling window; null for the other types | 
**CustomFrom** | **DateOnly** | First day chosen for a custom range; null for the other types | 
**CustomTo** | **DateOnly** | Last day chosen for a custom range, which can be after today; null for the other types | 
**From** | **DateOnly** | First day of the window as of now (detail only) | [optional] 
**To** | **DateOnly** | Last day of the window as of now (detail only); a custom range stops at today | [optional] 
**Label** | **string** | The window as the report shows it (detail only) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.TechnicalGeoReportContentUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**ReportType** | **string** | Only llms_txt reports have editable content | 
**ContentVersion** | **string** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale | 
**Edits** | [**TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


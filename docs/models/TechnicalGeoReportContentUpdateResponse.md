# LLMPulse.SDK.Model.TechnicalGeoReportContentUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | [optional] 
**ReportType** | **string** | Always llms_txt | [optional] 
**ProjectId** | **int** |  | [optional] 
**BatchId** | **int** | Bundle the report was created in; null for a report created on its own | [optional] 
**Url** | **string** | Always null for llms_txt reports; domain names the website | [optional] 
**Domain** | **string** |  | [optional] 
**CountryCode** | **string** |  | [optional] 
**OutputLanguageCode** | **string** | ISO 639-1 code the files were requested in; null when they are written in the website&#39;s own language | [optional] 
**Status** | **string** |  | [optional] 
**ResultAvailable** | **bool** |  | [optional] 
**OverallScore** | **decimal** | Always null for llms_txt reports | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 
**ResultData** | [**LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md) |  | [optional] 
**ErrorMessage** | **string** |  | [optional] 
**PollAfterSeconds** | **int** | Seconds to wait before polling again while the report runs; null once it has finished | [optional] 
**AppUrl** | **string** | Opens this report in the app | [optional] 
**RequestId** | **string** |  | [optional] 
**ChangedFiles** | **List&lt;TechnicalGeoReportContentUpdateResponse.ChangedFilesEnum&gt;** | Files whose text actually changed; empty when every file matched the stored text | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


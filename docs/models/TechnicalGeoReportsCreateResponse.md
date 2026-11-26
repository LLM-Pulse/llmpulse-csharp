# LLMPulse.SDK.Model.TechnicalGeoReportsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Url** | **string** | The URL analysed | 
**CountryCode** | **string** | The country used, the project country when none was sent | 
**OutputLanguageCode** | **string** | ISO 639-1 code the llms.txt files are written in, or auto for the website&#39;s own language | 
**CreatedReports** | **List&lt;string&gt;** | The report_type of every report created | 
**ReportIds** | **Dictionary&lt;string, int&gt;** | The id of each created report, by report_type | 
**AppUrls** | **Dictionary&lt;string, string&gt;** | The link that opens each created report in the app, by report_type | 
**FailedReports** | [**List&lt;TechnicalGeoReportsCreateResponseFailedReportsInner&gt;**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons | 
**NextEndpoint** | **string** | Path template to poll each created report | 
**PollAfterSeconds** | **int** | Seconds to wait before the first poll | 
**RequestId** | **string** |  | 
**BatchId** | **int** | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


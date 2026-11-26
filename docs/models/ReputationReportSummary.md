# LLMPulse.SDK.Model.ReputationReportSummary
One reputation or custom-study report's status and analyst model coverage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Report id for GET /reputation/reports/{id}, or GET /studies/{id}/reports/{report_id} for a study report | 
**Status** | **string** |  | 
**CreatedAt** | **DateTime** |  | 
**AvailableModels** | **List&lt;ReputationReportSummary.AvailableModelsEnum&gt;** | Analyst models that produced data | 
**MissingModels** | **List&lt;ReputationReportSummary.MissingModelsEnum&gt;** | Analyst models with no data yet | 
**ProcessedAt** | **DateTime** |  | [optional] 
**ErrorMessage** | **string** | Why the report failed; null unless status is failed | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


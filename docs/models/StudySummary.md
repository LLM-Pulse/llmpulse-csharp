# LLMPulse.SDK.Model.StudySummary
One custom AI study

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Title** | **string** |  | 
**StudyType** | **string** | brand_set, sector, geo, topic or custom | 
**Cadence** | **string** | one_shot or monthly | 
**Status** | **string** | active or archived | 
**SubjectsCount** | **int** |  | 
**AiModels** | **List&lt;StudySummary.AiModelsEnum&gt;** | Analyst models the study runs on | 
**OutputLanguageCode** | **string** | ISO 639-1 code of the language the reports are written in | 
**CreatedAt** | **DateTime** |  | 
**ProjectId** | **int** | The project the study is attached to; null for an account-level study | 
**LastReportAt** | **DateTime** | When the latest report started; null before the first one | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


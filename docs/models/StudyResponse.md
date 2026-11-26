# LLMPulse.SDK.Model.StudyResponse
One custom AI study with its brief, subjects, dimensions and latest reports

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Title** | **string** |  | 
**StudyType** | **string** | brand_set, sector, geo, topic or custom | 
**Cadence** | **string** | one_shot or monthly | 
**Status** | **string** | active or archived | 
**SubjectsCount** | **int** |  | 
**AiModels** | **List&lt;StudyResponse.AiModelsEnum&gt;** | Analyst models the study runs on | 
**OutputLanguageCode** | **string** | ISO 639-1 code of the language the reports are written in | 
**CreatedAt** | **DateTime** |  | 
**Subjects** | **List&lt;string&gt;** | Names of the subjects it compares | 
**Dimensions** | **List&lt;string&gt;** | Keys of the dimensions it scores, as the dimension filter takes them | 
**Reports** | [**List&lt;ReputationReportSummary&gt;**](ReputationReportSummary.md) | The 24 latest reports, newest first | 
**RequestId** | **string** |  | 
**ProjectId** | **int** | The project the study is attached to; null for an account-level study | 
**LastReportAt** | **DateTime** | When the latest report started; null before the first one | 
**Brief** | **string** | What the study asks the analyst models; null when none was written | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


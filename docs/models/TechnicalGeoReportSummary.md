# LLMPulse.SDK.Model.TechnicalGeoReportSummary
One technical GEO report's status and score

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**ReportType** | **string** | The report_type requested (agent_readiness for ai_readiness) | 
**ProjectId** | **int** |  | 
**Domain** | **string** |  | 
**Status** | **string** | Depends on report_type. Every type ends completed or failed; ai_visibility can also end insufficient_data | 
**ResultAvailable** | **bool** | Whether status is completed | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**BatchId** | **int** | Bundle the report was created in; null for a report created on its own | 
**Url** | **string** | The page analysed; null for the domain-level types (robots_txt, agent_readiness, llms_txt, ai_visibility) | 
**CountryCode** | **string** | Set only on llms_txt and ai_visibility reports | 
**OutputLanguageCode** | **string** | ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language and for every other type | 
**OverallScore** | **decimal** | Null until the report completes, and always for llms_txt | 
**AppUrl** | **string** | Opens this report in the app | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


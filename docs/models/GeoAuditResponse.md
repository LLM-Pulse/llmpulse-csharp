# LLMPulse.SDK.Model.GeoAuditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Stable audit id | [optional] 
**AuditType** | **string** |  | [optional] 
**Target** | **string** | The audited domain (site-wide types) or page URL, normalized | [optional] 
**CountryCode** | **string** |  | [optional] 
**Cadence** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**PausedReason** | **string** | user, or unreachable when three runs in a row could not reach the site | [optional] 
**Schedule** | [**GeoAuditSchedule**](GeoAuditSchedule.md) |  | [optional] 
**NextRunAt** | **DateTime** |  | [optional] 
**EmailAlerts** | **bool** |  | [optional] 
**RecurringAvailable** | **bool** | Whether this audit type can run weekly or monthly | [optional] 
**ChecksTracked** | **bool** | Whether runs of this type produce findings and issues, or a score only | [optional] 
**LatestRun** | [**GeoAuditRun**](GeoAuditRun.md) |  | [optional] 
**OpenIssues** | **int** |  | [optional] 
**OpenCriticalIssues** | **int** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**AppUrl** | **string** |  | [optional] 
**ProjectId** | **int** |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


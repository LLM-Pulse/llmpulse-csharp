# LLMPulse.SDK.Model.GeoAuditUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Cadence** | **string** |  | [optional] 
**ScheduleDay** | **int** | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. | [optional] 
**ScheduleHour** | **int** | Hour of the day, 0 to 23, in the audit time zone | [optional] 
**Status** | **string** | paused stops scheduled runs, active resumes them, archived is the same as DELETE | [optional] 
**EmailAlerts** | **bool** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


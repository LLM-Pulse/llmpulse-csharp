# LLMPulse.SDK.Model.GeoAuditCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Target** | **string** | The domain (site-wide types) or page URL to audit | 
**AuditTypes** | **List&lt;GeoAuditCreateRequest.AuditTypesEnum&gt;** | One or more audit types; each becomes its own audit and starts its first run | 
**Cadence** | **string** | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


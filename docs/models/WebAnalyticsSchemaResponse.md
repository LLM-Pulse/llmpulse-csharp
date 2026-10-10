# LLMPulse.SDK.Model.WebAnalyticsSchemaResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | [optional] 
**Provider** | **string** | The connected web analytics provider. | [optional] 
**Property** | **string** | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. | [optional] 
**QueryLanguage** | **string** | The native query format the provider accepts. | [optional] 
**DocsUrl** | **string** | The provider&#39;s reference for that format. | [optional] 
**AllowedFields** | **List&lt;string&gt;** | Top-level query fields that are forwarded. | [optional] 
**Rules** | **List&lt;string&gt;** | What the bridge enforces and the provider&#39;s main constraints. | [optional] 
**Example** | **Dictionary&lt;string, Object&gt;** | A worked query to adapt. | [optional] 
**Fields** | **Dictionary&lt;string, Object&gt;** | The provider&#39;s live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. | [optional] 
**FieldsUnavailable** | **string** | Present when the field list could not be read; the format and example still apply. | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.UrlListCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Name** | **string** |  | 
**Description** | **string** |  | [optional] 
**Currency** | **string** |  | [optional] [default to CurrencyEnum.USD]
**Entries** | [**List&lt;UrlListEntryInput&gt;**](UrlListEntryInput.md) |  | [optional] 
**MatchType** | **string** | Read every entry without its own match_type as this type. Default detects it from each value. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


# LLMPulse.SDK.Model.CreateTechnicalGeoReportsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Url** | **string** |  | 
**CountryCode** | **string** | Defaults to the project country | [optional] 
**OutputLanguageCode** | **string** | ISO 639-1 code of the language the llms.txt files are written in (for example es). Defaults to the project language, else en. Only the llms.txt report of the bundle uses it; an unsupported code returns 422 ERR_INVALID_PARAM | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


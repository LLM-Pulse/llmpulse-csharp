# LLMPulse.SDK.Model.PromptsImportRequestRowsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Prompt** | **string** | The prompt text, up to 2,000 bytes of UTF-8 text (about 2,000 characters in English, fewer with accented letters or non-Latin scripts). A longer new prompt skips the row, which comes back in row_errors; a row matching a prompt the project already tracks counts as a duplicate | 
**CountryCode** | **string** | ISO 3166-1 alpha-2 code or country name (default the project country) | [optional] 
**LanguageCode** | **string** | ISO language code or language name (default the project language) | [optional] 
**Tags** | **List&lt;string&gt;** | Tag names for this prompt, created when missing | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


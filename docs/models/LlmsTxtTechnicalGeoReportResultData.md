# LLMPulse.SDK.Model.LlmsTxtTechnicalGeoReportResultData
The files and generation details once the report has completed; null before that

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**LlmsTxtContent** | **string** | Current llms.txt, manual edits included | [optional] 
**LlmsFullTxtContent** | **string** | Current llms-full.txt, manual edits included | [optional] 
**ManuallyEditedAt** | **DateTime** | When the files were last edited by hand in the app, the API or MCP; null while they are as generated | [optional] 
**ContentVersion** | **string** | Send it back as content_version when editing the files. It changes on every save | [optional] 
**OriginalLlmsTxtContent** | **string** | The generated llms.txt, kept from the first manual edit; null while the files are as generated | [optional] 
**OriginalLlmsFullTxtContent** | **string** | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated | [optional] 
**CrawlData** | **Object** |  | [optional] 
**Metadata** | **Object** | Generation details, including output_language_code, the language the files were written in | [optional] 
**PagesCrawled** | **int** |  | [optional] 
**GenerationTimeMs** | **int** |  | [optional] 
**OpenaiTokensUsed** | **int** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


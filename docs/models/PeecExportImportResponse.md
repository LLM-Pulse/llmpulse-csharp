# LLMPulse.SDK.Model.PeecExportImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**ImportId** | **int** |  | 
**Status** | **string** | The import was accepted and finishes in the background | 
**Prompts** | **int** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project | 
**NewPrompts** | **int** | The prompts the project does not hold yet, counted against the plan | 
**PlannedAnswers** | **int** | Weekly answers the import files (prompts x tracked AI models x weeks) | 
**Models** | **Dictionary&lt;string, string&gt;** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under | 
**SkippedModels** | **List&lt;string&gt;** | AI model names of the file whose answers are skipped, because the account does not track them | 
**DetectedBrands** | **List&lt;string&gt;** | Brand names the export&#39;s mentions column lists (up to 50), none of them created as competitors | 
**AppUrl** | **string** | Opens the project&#39;s prompts in the app | 
**RequestId** | **string** |  | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


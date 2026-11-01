# LLMPulse.SDK.Model.ProjectDetailsAllOfPitchRun
The one run of a pitch project; null for a tracked project. Its answers are dated between launched_at and settled_at, so read its metrics with from set to the launched_at date (the default ranges leave out a pitch older than a few weeks)

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** | starting before the run begins, running while answers arrive, ready once every AI model has answered or stopped trying | [optional] 
**LaunchedAt** | **DateTime** |  | [optional] 
**SettledAt** | **DateTime** |  | [optional] 
**Models** | **List&lt;ProjectDetailsAllOfPitchRun.ModelsEnum&gt;** | The AI models the run asks, fixed when it starts | [optional] 
**AnswersExpected** | **int** |  | [optional] 
**AnswersReceived** | **int** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


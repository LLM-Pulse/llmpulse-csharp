# LLMPulse.SDK.Model.AnalystScoreRow
One analyst model's score of one brand (a subject in a custom study) on one attribute of one dimension

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Brand** | **string** | Brand name; the subject name in a custom study | 
**IsProject** | **bool** | Whether it is the project&#39;s own brand; in a custom study, the focus subject | 
**Model** | **string** |  | 
**ReportDate** | **DateOnly** |  | 
**Dimension** | **string** | Dimension key, as the dimension filter takes it | 
**DimensionName** | **string** |  | 
**Attribute** | **string** | Attribute key within the dimension | 
**AttributeName** | **string** |  | 
**Score** | **Object** | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model&#39;s output is stored without coercion | 
**Reasoning** | **string** | Why the model gave this score; null when it gave no reasoning | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

